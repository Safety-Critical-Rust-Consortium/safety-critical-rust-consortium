# Safety-Critical Rust Consortium Meeting on 2026-05-26 @ 12pm EDT / 6pm CEST

Expert session with Ralf Jung and Ben Kimock of the Rust Project Operational Semantics Team (t-opsem)

| Search Key | Description |
| :---- | :---- |
| \[todo\] | Action Item |
| \[decision\] | Something decided on |
| \[important\] | Key information |

## Agenda

1. Introduction to t-opsem  
2. Discuss

## Check-in area

**Please add your name, and an emoji that describes your day.**

* Pete LeVasseur 🦀✍️  
* Max Jacinto 👾💻  
* Andreas Weis   
* Kartik Ohlan   
* David de Rosier 🐠  
* Tiago Manczak  
* Erik Rose🌹  
* Christof Petig ⏲️  
* Roberto Bagnara 🏴‍☠️  
* Marcos Borges 🤯  
* Félix Fischer ☕  
* Marc Schoolderman 🥪  
* Samuel Wright 🍽️

**Notetaker:**

* Pete LeVasseur

## Housekeeping section

* 

## Tasks

* Andreas Weiss to come back with small, self-contained examples of the kinds of “gray zone” areas of soundness / definedness which still would make sense in the larger context of iceoryx2

## Meeting Minutes

## Introduction to t-opsem

* The truly settled items are in the Reference and in the standard library docs

FCP \- *Final Comment Period*

* Mechanism by which teams agree  
* List of current FCPs where the opsem team has reached consensus on: [https://github.com/rust-lang/opsem-team/blob/main/fcps.md](https://github.com/rust-lang/opsem-team/blob/main/fcps.md)  
* List is most likely incomplete (it is updated by hand)

**Note**: regarding the UCG / Unsafe Code Guidelines Reference

* **Not complete, basically unmaintained.**  
* The document exists for historical reference.  
* **The Glossary** can be used as an informative reference. The guidelines cannot.  
* [https://rust-lang.github.io/unsafe-code-guidelines/](https://rust-lang.github.io/unsafe-code-guidelines/)

Important opsem tooling: Miri

* The **MIR** **i**nterpreter  
* [https://github.com/rust-lang/miri](https://github.com/rust-lang/miri)  
* Latest paper about miri: [(2026) Miri: Practical Undefined Behavior Detection for Rust](https://plf.inf.ethz.ch/research/popl26-miri.html)

Mini Rust talk given at last year’s RustWeek 2025

* [MiniRust: A core language for specifying Rust \- Ralf Jung](https://www.youtube.com/watch?v=yoeuW_dSe0o)

Making progress on some OpSem questions requires stakeholders outside the Rust project.

* E.g. make sure that LLVM does the right thing  
* Mapping same memory into multiple address spaces kicks out a potentially large number of optimizations that LLVM does

## Eclipse iceoryx2 \- shared memory, zero-copy transport

* Written in Rust  
* Going to safety-certify  
* Working to understand the Rust reference and the standard library docs to make sure we know how to rest a safety argument on normative documentation

Shared memory, for example, seems challenging to describe accurately via the Rust Abstract Machine

* Use-case for library 2 different processes that map the same memory to their address space  
* Could also be used from single process; in that case same memory mapped into two spots in same address space  
* Would like to put atomics to be able to reason about “when” changes are made

Same memory segment mapped to different addresses

* Pointers don’t work anymore  
* Need to discuss in terms of offsets  
* Use own address as base for the offset  
* Found it difficult to implement this reasonably

In preparation put together small document that describes constructs that may be problematic

* [https://github.com/ekxide/iox2-scrc-examples/blob/main/README.md](https://github.com/ekxide/iox2-scrc-examples/blob/main/README.md)

Use case: being able to put complex data structures into shared memory and then interact with the shared memory objects “like normal” is a key thing that’s valuable

* Publishing a hashmap, such as being able to make changes right in place  
* The subscriber side still wants to be able to make lookups into the hashmap

What is the “trust relationship” in entities among iceoryx2?

* Difficult scenario \-- safety-critical, mixed criticality systems. Need to ensure that subscriber is low-criticality it cannot compromise a higher-criticality publisher.  
* Constraint: Want to ensure if low-criticality process dies this does not compromise a high-criticality one  
  * Unable to do locks, lock-free

Hard problems in opsem

* Two processes which do not trust each other, how can they share data  
* No clear way of going about this on the LLVM side
* Let alone when it comes to how to specify this in the Rust Abstract Machine  
* An important detail is that what simplifies things is if it follows the aliasing XOR mutation discipline is upheld: either only one side can mutate *while nobody else can even read*, or everybody can only read.

Want to ensure that iceoryx2 takes care of some of the complications

* E.g. in Subscriber side, map only as read-only segment to prevent common issues

Can one side read, while the other side is writing?

* Quite hard; limitation of operating systems  
* Is it the case that at any time one side is reading while the other side is writing?  
  * No; but could be abstracted over in the Rust Abstract Machine  
* Attempt to make APIs which respect Rust’s model  
  * Useful article: [How to use storytelling to fit inline assembly into Rust](https://www.ralfj.de/blog/2026/03/13/inline-asm.html)    
  * If can be reframed in the model from the above blog post, then don’t need language or compiler changes.  
  * Wrapping in inline assembly code can prevent optimizations from being run which would break the program  
  * Is this formalized?  
    * No, but there’s a line of argumentation that could be used  
    * Not put into a theorem prover yet  
  * One idea for project goal might be to involve this towards being accepted normatively

Mechanism of working together

* Attempt to write safety comments on each gray zone usage of **`unsafe`**  
* For those which we cannot have a safety comment written from normative locations (Reference, Standard library docs) gather them up

### Feedback on 5: Uninitialized memory one

* How do you know the memory doesn’t contain the magic bit pattern at the outset?  
* Operating system guarantees that raw memory block is given that is zero initialized (sbreak sp?)  
* Then could say that Rust Abstract Machine guarantees this as well (confirm this?)  
* Memory could become deinitialized  
  * If **memcpy** from A \=\> B then could copy over uninitialized memory mistakenly making the destination deinitialized  
* In the Abstract Machine anything padding between fields is not copied over  
  * Layout is assumed fixed and known in an earlier part of the compiler  
  * E.g. **(u8, u16)** tuple if copied over, then the destination would have that padding byte be uninitialized as the last item in the tuple is not reordered (not stable behavior)

Can just pretend mmap is a “weird” version of malloc/calloc to make some safety arguments

* If mmap allows for things like punching holes in allocations or extending them, then that is different

Rust Abstract Machine

* Can just pretend that every function call could do what malloc could  
* Need to do some sort of “storytelling” in the language of the Abstract Machine  
  * As long as no overlap of memory with what would be handed out by Rust Abstract Machine, e.g. anything that need to be put onto the heap

### Feedback on 7: Benign reads of padding bytes

* Whenever reading data, including padding bytes, as **u8**  
* Want to be able to read them as a series of **u8** even if they are uninitialized, since we don’t care about the value of the bytes  
* Would simply reading them already put you in trouble? Do we need to skip over the holes of the padding bytes?  
  * Cannot read as **u8**, but can read as **MaybeUninit\<u8\>**  
  * **u8** is really a number in Rust, unlike C; so if you load it, it needs to be initialized memory as a **u8** in a legal value  
  * Allows copying of bytes from A \=\> B without interpreting their value  
* Would this also work with atomic access?  
  * No way to do this on potentially uninitialized memory  
  * There is a crate someone wrote with uses inline assembly (least incorrect way of doing this, since it hides as much information from the compiler as possible)  
  * No reason it cannot exist, but someone would need to do the work to specify this and   
  * Load and store are possible, but nothing barring from doing this from an opsem perspective  
  * Compare and Swap doesn’t make sense with uninitialized memory

### Feedback on 6: Sequence Locks

* **UnrestrictedAtomic** type seems the right path, but blocked on LLVM  
  * Has been blocked for \~3 years or so on the C++ side of things  
  * Might have been due to ISO standards concerns  
* Want this added for monotonic atomics, which is called ***Relaxed memory ordering*** in Rust  
* No fundamental issues with doing this in Rust afterwards  
* Should be enough at that point for doing a Sequence Lock  
* Perhaps should get in touch with person at Google that works on the C++ portion of LLVM  
  * \[TODO\] Andreas \+ Pete to reach out

### Feedback on 1: [Hidden Aliasing Through Shared Memory](https://github.com/ekxide/iox2-scrc-examples/blob/main/README.md#example-1---hidden-aliasing-through-shared-memory)

* Idea is to, with the iceoryx2 APIs, hide the “ugly” aspects of doing shared memory from the user  
* Publisher requests memory segment to write into, can make changes within constraints of payload type to send  
* Once published, no pointers are retained to that shared memory on the publisher  
* That way on the Subscriber side there’s assurance the memory contents are changed no more  
* Ensure to not re-use memory so long as there’s still some references to it  
* Is this like each time **loan\_init()** is called, then we get a new fresh thing which doesn’t interact with anything else?  
  * Conceptually yes  
  * In practice, it’s reused when can be sure not any other references  
  * Answer: Conceptually seems totally fine, would need to put some kind of empty inline assembly block as a barrier  
    * How to deal with pages mapped into multiple address spaces \-- in Rust Abstract Machine terms  
    * There is realloc; could “pretend” and split runtime of program into Phase A, Phase B, Phase C would then make this remotely correct to run through an optimizing compiler  
    * When going from Phase X \=\> Y then you can invalidate all the old pointers  
    * Allows for implementing as empty inline assembly block as input  
      * Give old pointer, return new pointer  
      * Don’t need to exist in assembly  
      * Allows for reasoning about this in terms of the Rust Abstract Machine  
      * (This was the hope of Eclipse iceoryx2)  
    * What does the “magical incantation” look like?  
    * Related to the blog post shared; need to make argument under that reasoning of the Rust Abstract Machine using inline assembly  
    * Related RFC for “fake” **realloc**, useful for ARM architectures to make some portion of it a magic token: [RFC 3700: ptr::assume::moved](https://github.com/mrkajetanp/rfcs/blob/ptr-tag-helpers/text/3700-ptr-assume-moved.md)  
* Publisher and subscribers in this example are in the same process  
  * When peeking at their addresses, they appear to be pointing to different places  
  * But they are actually pointing at the same underlying memory  
  * “Hidden aliasing”  
  * **realloc** idea in that case will not work  
    * Litmus test: can we come up with a Rust Abstract Machine story to tell?  
      * So long as both of them are read-only, shouldn’t be too hard  
      * Doesn’t need to mean they are read-only at the hardware level, could be logically: *“is it **supposed to** be read from?”*  
      * The empty inline assembly block creates two new read-only allocations, put the source into both of them and mark as read-only  
        * “Mark as read-only” is not currently an operation in the AM  
        * Fine, but needs a bit of specification work  
        * Only important that the program doesn’t write it, doesn’t need to be “true” at the hardware level  
  * Further complication: the sample the user receives is read-only; the memory segment that reads in needs to be writable to communicate to the publisher side when done reading  
    * Book-keeping data structures are written to by the Subscriber  
      * Also duplicated in address space?  
        * That’s a lot harder and may not be able to be deeply formally justified  
        * Would have to dig into the code; need to carefully investigate

## Closing the meeting: **next steps in this conversation?**

* Identify the most interesting places in the implementation that touches on the key concepts discussed today?  
* Create smaller implementations to investigate?  
  * This route is more helpful for discussion  
  * Could be put into the t-opsem Zulip chat; get larger support without a need to read entirety of iceoryx2  
  * Small reproducible bits of code that are concrete are useful to review by t-opsem  
    * Need to be careful in carrying over what’s learned into the main library  
  * Need to ensure small examples make the same sorts of assumptions  
  * Exact MMAP interactions become important, so having those details exposed would be worthwhile  
    * Could get to a state where we can lean on the MMAP implementation in Miri (currently somewhat limited) to allow for spelling out the model in code, within Miri  
    * May be able to build shim for iceoryx2   
* When would we be able to have the small set of reproducible examples?  
  * Maybe 3-4 weeks’ time  
  * Get help from colleagues in putting the small reproducible together

## Material

Any material to read before the meeting should be included here.

* 

