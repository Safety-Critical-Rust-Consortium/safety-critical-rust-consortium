# **Coding Guidelines Subcommittee Meeting on 2026-09-02 @ 1600 CEST / 1100 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-9-2&sln=11-12&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker  
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-08-28/minutes.md)  
3. Introduction of new members  
4. Walk through [Analysis of Difference to MISRust](https://github.com/inkreasing/safety-critical-rust-coding-guidelines/blob/misrust/src/appendices/standards-matrices/differences-to-misrust.rst) (Mira)  
   - Mira's analysis compares the Consortium's MISRA C++:2023 mapping with the classifications and rationales in MISRust  
   - Goal: discuss differing classifications and rationales and identify any follow-up changes for the Consortium's mapping  
   - Supporting references: [MISRust paper](https://arxiv.org/abs/2605.23490), [MISRust repository](https://github.com/embedded-software-laboratory/MISRust), and [rule-by-rule mapping](https://github.com/embedded-software-laboratory/MISRust/blob/main/misra_cpp_rust_comparison_rules.csv)  
5. Working session: continue reviewing the MISRA C++:2023 to Rust coding guidelines mapping (Mira / Pete)  
   - Parent tracking issue: [\#575 Mapping for MISRA C++:2023 to Rust Guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)  
   - Initial documentation PR: [\#1226 Add the MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)  
   - [Working spreadsheet](https://docs.google.com/spreadsheets/d/12e9Tr8PUTvVr87nUH0MQTwL31yU6YihQVxlvkqlo9SA/edit?gid=0#gid=0), currently reporting 179/179 guidelines analyzed  
   - Reference: [MathWorks listing of MISRA C++:2023 rules and directives](https://www.mathworks.com/help/bugfinder/misra-cpp-2023-rules-and-directives.html)  
   - Review history: [August 26 minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-08-26/minutes.md) and [August 28 minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-08-28/minutes.md)  
   - The scopes below contain only mappings without review comments on PR \#1226 as of September 1 and not recorded as reviewed in previous working sessions  
   - Goal: confirm or revise each proposed Rust categorization and capture decisions and follow-up work in the tracking issue and PR  
   - **Group A \- mappings applicable to Rust in general**  
     - Scope (15 mappings): Rules 0.0.1, 0.0.2, 0.1.1, 0.1.2, 0.2.1, 0.2.2, 0.2.3, and 0.2.4; Directives 0.3.1 and 0.3.2; Rule 5.7.1; Directive 5.7.2; and Rules 5.13.4, 8.0.1, and 28.6.1  
     - [https://meet.google.com/zyp-fmsy-xxv](https://meet.google.com/zyp-fmsy-xxv)  
     - Group:  
       1. Daniel Dia 🍹  
       2. Samuel Wright   
       3. Mira Baumann ☕  
       4. Oreste Bernardi 📋

   - **Group B \- mappings additionally applicable in the presence of unsafe code**  
     - Scope (15 mappings): Rules 6.2.1, 6.2.2, 6.5.1, and 6.5.2; Directive 15.8.1; and Rules 21.10.1, 21.10.2, 21.10.3, 22.4.1, 23.11.1, 24.5.2, 25.5.1, 25.5.2, 25.5.3, and 28.6.3  
     - [https://meet.google.com/ifx-utwa-frn](https://meet.google.com/ifx-utwa-frn)  
     - Group:  
       1. William Barsse  
       2. Christof Petig ⏲️  
       3. Alex Celeste ☕  
       4. Jeongsoo Lee 🥛  
       5. Achim Kriso 🦆  
2. Round table

   ## **Check-in area**

- Daniel Dia 🍹  
- Samuel Wright   
- Mira Baumann ☕  
- Oreste Bernardi 📋  
- William Barsse  
- Christof Petig ⏲️  
- Alex Celeste ☕  
- Jeongsoo Lee 🥛  
- Achim Kriso 🦆

  **Notetaker:**

- Alex Celeste

  For tips on how we take notes in the Safety-Critical Rust Consortium, please see the [Meeting Notetaker Role](https://github.com/rustfoundation/safety-critical-rust-consortium/blob/main/docs/notetaker-role.md) doc.

  ## **Housekeeping section**

- Document space: [coding-guidelines](https://github.com/rustfoundation/safety-critical-rust-consortium/tree/main/subcommittee/coding-guidelines)  
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)  
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)  
  - [`contributor experience`](https://github.com/orgs/rustfoundation/projects/1/views/4) view  
  - [`coding guideline`](https://github.com/orgs/rustfoundation/projects/1/views/5) view

  ## **Tasks**

- \[todo\] Achim to update the mapping PR with decisions from group B

  ## **Meeting Minutes**

- Acceptance of previous minutes without objection.  
- Presenting the MISRust paper (see linked Material);  
  - separate analysis; six basic categories to our three, possibly to imitate;  
  - find 11 unsafe Rust rules requiring adoption, but do not recommend adoption of safe Rust rules  
    - “Rust-specific adaptation potentially required” with unclear impact  
  - also considered lints, which cover e.g. MISRA Rule 0.0.1 arguing that this does *not* support adaptation  
    - C++ tooling also has such lints and analyses which support rather than obsolete rules  
    - rustc lints cannot consider impact of e.g. callouts to C code  
    - e.g. 7.0.4 shift-out-of-bounds: trivially easy to rewrite code to not trigger lints (i.e. by needing whole-program/dataflow analysis which is not provided, even within const)  
    - this impacts a large number of rules  
  - inaccuracies in some of the analyses, potential errors  
    - presentation of the analyses is unclear to the point of total misinterpretation  
  - not worthless but too many mistakes to be pursuing in detail, except for toplevel ideas like classification  
    - errors discredit the rest of the paper  
    - extremely different interpretations of rationale for some of the rules, to the point of disagreeing on application  
  - a full table of differences presented, marking where our mapping should be reviewed  
    - some contradictions and overlaps with the MISRA C mapping  
- Review of the MISRA C++ Guidelines mapping  
  - A:  
    - …  
    - Mostly agreed that language-independent rules still apply to Rust, depending on the definition of “unexpected” behavior  
      1. For undefined behavior  
      2. Not for panics (“more discussion needed”)  
  - B:  
    - 6.2.1, violating the one-definition rule:  
      1. can this be violated by the \`no-mangle\` attribute? Two different symbols can be produced without module disambiguation  
      2. which symbol gets linked is explicitly listed in the documentation as unspecified  
      3. Weak symbols (arguably a violation, outside of the language definition)  
      4. The linker may or may not catch such things depending on which linker is actually in use  
         1. A linker is provided in the toolchain but may not be the one used by the project  
      5. Agree that this **is** applicable  
    - 6.2.2, all declarations shall have the same type  
      1. Enforced within Rust by the compiler  
      2. FFI doesn’t enforce this and cannot really enforce this (inc. between crates)  
      3. Agree that this **is** applicable (in the same way as the table presented in the rule)  
    - 6.5.1, declarations go in header files  
      1. Not really an analogous concept in Rust  
      2. extern “C” blocks exist, but does it matter where they are placed within the module?  
         1. A rule about this wouldn’t be the same rule, to e.g. to put all declarations together, “contain your minefields in one place”  
         2. It *is* possible to generate colliding names  
      3. Rule is **not** applicable as-written  
         1. A new sibling rule is justified  
    - 6.5.2, specify internal linkage  
      1. Seems to be fully covered by the module system already  
      2. This is about *how* to express in C++ rather than what is being expressed  
      3. Odd interplay with 6.2.4  
      4. Agree that this **is not** applicable  
    - 15.8.1 handle self-assignment in assignment operators  
      1. Related to 15.0.1  
      2. argue that Rust doesn’t have these rule of three/five/zero problems by construction  
         1. Rust arguably has a Rule of Two, basis for a new rule  
         2. Distinct sibling rule rather than direct application  
      3. Mira’s analysis argues that this shouldn’t apply  
      4. Rule is **not** applicable as-written  
         1. A new sibling rule is justified  
    - 21.10.1 don’t use cstdarg/stdarg.h  
      1. Rust already has a variadic mechanism provided by Rust macros  
         1. Which is not vulnerable to the issues expressed in the Rationale  
         2. and there is an exception for *use* of ellipsis-functions  
      2. These features aren’t really able to be imported directly  
         1. Exist entirely on the C and C++ side of the FFI  
         2. There are RFCs (2137) to provide a parallel to va\_list such that it could be manipulated from the Rust side  
      3. Not needed in order to *use* variadic C functions like printf, only in their definition  
      4. A parallel rule should be added if the RFC is adopted  
         1. does appear to have been merged already ([https://github.com/rust-lang/rust/pull/155697](https://github.com/rust-lang/rust/pull/155697))  
      5. Rule is **not** applicable as-written  
         1. A new sibling rule **should** be written because there’s a new UB in the RFC, but needs own phrasing  
- Round table  
  - [https://www.sonair.com/journal/how-we-safety-certified-the-worlds-first-rust-implementation](https://www.sonair.com/journal/how-we-safety-certified-the-worlds-first-rust-implementation)  
    - Worked with Ferrocene, started before the compiler itself was certified, dependencies were the biggest difficulty and had to be either rewritten or increase test coverage to reach required coverage level  
    - “Worth it”  
- Adjourned

  ## **Material**

  Meeting-specific reading:

- [Mira's analysis of differences to MISRust](https://github.com/inkreasing/safety-critical-rust-coding-guidelines/blob/misrust/src/appendices/standards-matrices/differences-to-misrust.rst)  
- [MISRust paper](https://arxiv.org/abs/2605.23490)  
- [MISRust supporting artifacts](https://github.com/embedded-software-laboratory/MISRust)

  Overview of [Safety-Critical Rust](https://rust-lang.github.io/rust-project-goals/2026/roadmap-safety-critical-rust.html) Rust Project Goals Roadmap (Pete)

- Soliciting those interested in [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html) goal  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip  
- Soliciting those interested in [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html) goal  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip
