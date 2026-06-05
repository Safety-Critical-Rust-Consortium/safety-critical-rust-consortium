# Safety-Critical Rust Consortium Meeting on 2026-05-27 @ 10am EDT / 4pm CEST

Expert session with Jason Newcomb of the Rust Project Clippy Team (t-clippy)

| Search Key | Description |
| :---- | :---- |
| \[todo\] | Action Item |
| \[decision\] | Something decided on |
| \[important\] | Key information |

## Agenda

1. Introduction to t-clippy  
2. Practical guide to writing Clippy lints

## Check-in area

**Please add your name, and an emoji that describes your day.**

* David Svoboda (-:  
* Jason Newcomb  
* Michael Henn 🥵  
* Manuel Hatzl ☀️  
* Samuel Wright 🌞  
* Arshad Mahmood 🌅  
* Max Jacinto 🍀  
* Pete LeVasseur 🦀🦺  
* Mira Baumann 🧵  
* Raiki Tamura🏫  
* Achim Kriso 🦆  
* Mikhail Antoshkin 💤  
* William Barsse  
* Marcos Borges 😎  
* Christof Petig 🥵

**Notetaker:**

* Pete LeVasseur

## Housekeeping section

* 

## Tasks

* 

## Meeting Minutes

## Introduction to t-clippy

Clippy Book / Getting Started Guide

* [https://doc.rust-lang.org/nightly/clippy/development/infrastructure/book.html](https://doc.rust-lang.org/nightly/clippy/development/infrastructure/book.html)

Who has worked on/with Clippy?

* Pete LeVasseur  
* Arshad Mahmood  
* Achim Kriso

Who has worked on/with static analysis tools in the past?

* David Svoboda

Differing levels of where you can “hook into”

* Syntax/AST  
* HIR  
* MIR

Can we have the lints be put into their own Safety-Critical Rust grouping (to Jason Newcomb)?

* Jason will bring this forward to the team and discuss the idea  
* Might or might not be a need for this depending on (1) how many lints we are writing (2) how 

Can we have lints that overlap between different groups?

* Technically possible today  
* Prefer to not do this  
* Jason would need to bring this back to the team to discuss the usecase of safety-critical to be able to “turn on all the things”

Starting point

* `cargo dev new_lint -h` for reading how to create a new lint  
* Also read: [https://doc.rust-lang.org/nightly/clippy/development/infrastructure/book.html](https://doc.rust-lang.org/nightly/clippy/development/infrastructure/book.html)  
* Basic scaffolding will be set up  
  * “Lint pass” to hook into compiler’s infrastructure  
    * Could be any number of lints in a single lint pass  
* Lint pass runs as visitor over entire HIR tree  
  * Can then define `check_expr` on the `LateLintPass` which will run over every expression node in the HIR tree  
  * Can then define `check_body` as well as an alternative type of item to check  
  * Many, many hooks are available to you in here to hook into the visitor

In `check_expr`:

* Tend to first do some sort of filtering to find the type of expression that you’d like to lint on  
  * `match e.kind { /* .. */ }`  
  * Can then filter onto e.g. `ExprKind::Path`  
    * Can allow for destructuring and further filtering  
* Entails reading a lot of compiler documentation to understand how to check over HIR  
  * [https://doc.rust-lang.org/nightly/nightly-rustc/](https://doc.rust-lang.org/nightly/nightly-rustc/)  
  * [https://rustc-dev-guide.rust-lang.org/](https://rustc-dev-guide.rust-lang.org/)  
  * [https://github.com/rust-lang/rust-clippy/tree/master/book/src/development](https://github.com/rust-lang/rust-clippy/tree/master/book/src/development)  
  * Some things are documented, some things are not  
  * May, at times, need to look at compiler source code  
* Can further filter, e.g.  
  * `match p { QPath::Resolved(/* .. */) => { /* .. */ }, /* .. */ }`  
* Many, many hooks are available to you in here

The tests and how to work with them

* Ends up being named the same as the lint that you named  
* All lints run on all files (dogfooding)  
* If a new lint triggers on other files, you can tell them to ignore the new lint  
  * When writing test, then default enabled things run at the same time  
  * Could cause it to take some time to run at first  
  * Normally then handle this with a targeted `#![allow(clippy::other_failing_lint_we_dont_care_about)]`  
* There are `your_lint_here.stderr` files which contain the expected output of the lint that this is checked against

The mindset

* Write a test which is “normal” and represents where the lint should fire  
* Write the the lint logic  
* Go run the lints  
* Note that it may fail or not catch what we want  
* Once it does, run the `bless` command and go back and write another test, then flesh out the lint more in a loop

Question: Is there some kind of workflow / secret that will not be on the documentation?

* No, not really  
* All of what Jason is walking us through is available in the documentation  
* Some of the things “not in” the Clippy documentation could be where as a lint implementor you have to get into how the compiler works, ASTs, HIR, MIR

Question: How about a more complex lint? Like constant propagation?

* Please hang tight, we’ll come back to this

`LateLintPass` details for HIR

* Doesn’t contain type information  
* Second parameter of `LateContext` will give useful information  
  * `cx.typeck_results()` will contain all the type checking information  
  * Can work with this further, e.g. `typeck.expr_ty(e)`  
* There is a helper function to use for checking on trait implementation  
  * `implements_trait!()`  
* Also have access to e.g. `cx.tcx.lang_items().eq_trait()` for getting the trait’s definition ID  
* Depending on if the trait has generics, there’s now an assert which forces passing this information that’s relevant in  
* Can resolve method calls, e.g. `ExprKind::MethodCall(/* .. */) => { def_id = typeck.type_dependent_def_id(e.hir_id) }`  
  * This information must be obtained like above  
* Other useful things like diagnostic items, e.g. `cx.tcs.is_diagnostic_item(name, did)`  
  * You’ll need to check the compiler documentation for this  
  * Jump to definition will take you to compiler source so you can get that info that’s decorated on the item: `rustc_diagnostic_item`  
* Helpful at times when filtering to “do the opposite of what the check is for”  
* When referring to typechecked item, goes back to the trait, not the implementation of the trait  
  * If “is this String’s implementation of something?” have to check type and Definition ID (def\_id)

`LateLintPass` details for MIR

* `check_fn()` or `check_body()`  
* `check_fn()` may also handle closures  
* First need to write a check for if MIR can be obtained  
  * If something can never be satisfied, then the MIR body never exists  
  * Would crash if trying to obtain  
* Work on optimized MIR  
* Perform whole MIR lint check on the body  
* For data flow analysis there’s fixed point analysis framework that allows to go MIR block by MIR block using the `Analysis` trait ([rustc\_mir\_dataflow](https://doc.rust-lang.org/beta/nightly-rustc/rustc_mir_dataflow/))  
  * Propagate until you run out of checks/changes to perform  
* Not a lot specific to doing const propagation  
  * Likely need to write your own code to handle this

Because lints are run on macro-expanded code

* You have to do some things to figure out if that’s the case  
* On each node you have the span  
  * `e.span.ctxt()` \=\> syntax context  
* Unique syntax context for each  
  * macro expansion and   
  * AST \=\> HIR lowering  
* Syntax context allows for telling when this expansion or lowering has occurred  
  * `e.span.ctxt().outer_expn_data()`  
  * Would end up with two different macro expansion context  
* When writing lints you may need to keep track of this; these can show up anywhere  
  * Any given `x` and `y` might originate from a macro expansion  
  * For style lints this matters and you have to compare context a lot along the way  
  * `e.span.ctxt() == p.span.ctxt()`  
    * Checking if the context of the parent thing is the same as the expression under investigation

Ways to solicit help / support:

* If writing a lint and stuck \=\> open a draft PR  
* If stuck, can open a topic on the Rust Zulip’s clippy channel

## Material

Any material to read before the meeting should be included here.

* 

