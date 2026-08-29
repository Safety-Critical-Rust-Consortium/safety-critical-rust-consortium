# **Coding Guidelines Subcommittee Meeting on 2026-08-26 @ 1600 CEST / 1100 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-8-26&sln=11-12&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker  
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-08-19/minutes.md)  
3. Introduction of new members  
4. Read and discuss [MISRust: Mapping MISRA-C++ Coding Guidelines to the Rust Programming Language](https://arxiv.org/abs/2605.23490) (Pete)  
   - MISRust is an independent rule-by-rule attempt to classify the applicability of all 179 MISRA C++:2023 guidelines to Rust  
   - Suggested reading: the abstract and Sections 3 and 4, covering the six-category classification framework and results  
   - Supporting artifacts: [MISRust repository](https://github.com/embedded-software-laboratory/MISRust) and [rule-by-rule mapping](https://github.com/embedded-software-laboratory/MISRust/blob/main/misra_cpp_rust_comparison_rules.csv)  
   - Maybe today, maybe when completed with our MISRA C++ => Rust mapping: compare the classification approaches, treatment of safe and unsafe Rust, and notable agreements or differences with the Consortium's mapping  
5. Working session: continue reviewing the MISRA C++:2023 to Rust coding guidelines mapping (Mira / Pete)  
   - Initial documentation PR: [#1226 Add the MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)  
   - Reference: [MathWorks listing of MISRA C++:2023 rules and directives](https://www.mathworks.com/help/bugfinder/misra-cpp-2023-rules-and-directives.html)  
   - Goal: confirm or revise each proposed Rust categorization and capture decisions and follow-up work in the tracking issue and PR  
   - **Group A - mappings applicable to Rust in general**  
     - Scope (12 mappings): Rules 11.3.2, 15.0.1, 16.6.1, 18.4.1, 18.5.1, 18.5.2, 19.0.2, 19.0.3, 19.2.1, 19.3.4, 21.2.3, and 21.6.1  
     - Group:  
       1. xx  
   - **Group B - mappings additionally applicable in the presence of unsafe code**  
     - Scope (9 mappings): Directive 15.8.1 and Rules 18.1.1, 21.6.5, 21.10.1, 21.10.2, 21.10.3, 22.4.1, 23.11.1, and 24.5.2  
     - Group:  
       1. xx  
6. Round table

## **Check-in area**

- xx
- xx
- xx
- xx
- xx
- xx
- xx
- xx
- xx
- xx
- xx
- xx

**Notetaker:**

- xx

For tips on how we take notes in the Safety-Critical Rust Consortium, please see the [Meeting Notetaker Role](https://github.com/rustfoundation/safety-critical-rust-consortium/blob/main/docs/notetaker-role.md) doc.

## **Housekeeping section**

- Document space: [coding-guidelines](https://github.com/rustfoundation/safety-critical-rust-consortium/tree/main/subcommittee/coding-guidelines)  
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)  
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)  
  - [`contributor experience`](https://github.com/orgs/rustfoundation/projects/1/views/4) view  
  - [`coding guideline`](https://github.com/orgs/rustfoundation/projects/1/views/5) view

## **Tasks**

- xx

## **Meeting Minutes**

- xx

## **Material**

Meeting-specific reading:

- [MISRust paper](https://arxiv.org/abs/2605.23490), particularly the abstract and Sections 3 and 4  
- [MISRust supporting artifacts](https://github.com/embedded-software-laboratory/MISRust)

Overview of [Safety-Critical Rust](https://rust-lang.github.io/rust-project-goals/2026/roadmap-safety-critical-rust.html) Rust Project Goals Roadmap (Pete)

- Soliciting those interested in [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html) goal  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip  
- Soliciting those interested in [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html) goal  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip
