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
   - Maybe today, maybe when completed with our MISRA C++ \=\> Rust mapping: compare the classification approaches, treatment of safe and unsafe Rust, and notable agreements or differences with the Consortium's mapping
5. Working session: continue reviewing the MISRA C++:2023 to Rust coding guidelines mapping (Mira / Pete)
   - Initial documentation PR: [\#1226 Add the MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)
   - Reference: [MathWorks listing of MISRA C++:2023 rules and directives](https://www.mathworks.com/help/bugfinder/misra-cpp-2023-rules-and-directives.html)
   - Goal: confirm or revise each proposed Rust categorization and capture decisions and follow-up work in the tracking issue and PR
   - **Group A \- mappings applicable to Rust in general**
     - Scope (12 mappings): Rules **11.3.2, 15.0.1, 16.6.1, 18.4.1, 18.5.1, 18.5.2, 19.0.2, 19.0.3, 19.2.1, 19.3.4, 21.2.3,** and 21.6.1

6. Round table

   ## **Check-in area**

- Pete LeVasseur 🚘
- Daniel Dia 🩵
- Douglas Deslauriers 🪡
- Max Jacinto 🐹
- Mira Baumann 🦔
- Jeongsoo Lee 🚀
- Achim Kriso 🦆
- Kangwon Lee 🤖

  **Notetaker:**

- Douglas Deslauriers

  For tips on how we take notes in the Safety-Critical Rust Consortium, please see the [Meeting Notetaker Role](https://github.com/rustfoundation/safety-critical-rust-consortium/blob/main/docs/notetaker-role.md) doc.

  ## **Housekeeping section**

- Document space: [coding-guidelines](https://github.com/rustfoundation/safety-critical-rust-consortium/tree/main/subcommittee/coding-guidelines)
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)
  - [`contributor experience`](https://github.com/orgs/rustfoundation/projects/1/views/4) view
  - [`coding guideline`](https://github.com/orgs/rustfoundation/projects/1/views/5) view

  ## **Tasks**

- \[Pete\] Contact the group who wrote MISRust to have a little discussion, perhaps an invite to our meeting.
- \[Max\] Open an issue on the coding guidelines repository to consider adding process documentation for the mapping rules.

  ## **Meeting Minutes**

- Previous Meeting minutes
  - Accepted, no dissent.
- MISRust Discussion
  - Peter found this paper which independently mapped MISRA C++ to Rust.
  - Silent reading of the abstract/introduction occurred as group.
  - For those interested, it would be good to read the rest of the document.
  - This group has discussed a lot about safe Rust/unsafe Rust in the context of mappings, which this document has explicitly spelled out and written down. Perhaps we should do the same.
  - Spelling out how the mappings should be separated would be good for async work. The graphic in Figure 2\. looks to be a good example.
- Working Session
  - Decided the group was small to not split, and stayed with Group A
  - Further notes of this session will on the [MISRA C++ to Rust mapping PR](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226#pullrequestreview-5032267376)
  - Was able to review 11.3.2, 15.0.1, 16.6.1, 18.4.1, 18.5.1, 18.5.2, 19.0.2, 19.0.3, 19.2.1, 19.3.4, 21.2.3
  - Pete has contacted MISRA leadership again and they seem to be close to finishing a round of edits on MISRA C++. Hope to have an SCRC organizational copy in the next two weeks.

  ## **Material**

  Meeting-specific reading:

- [MISRust paper](https://arxiv.org/abs/2605.23490), particularly the abstract and Sections 3 and 4
- [MISRust supporting artifacts](https://github.com/embedded-software-laboratory/MISRust)

  Overview of [Safety-Critical Rust](https://rust-lang.github.io/rust-project-goals/2026/roadmap-safety-critical-rust.html) Rust Project Goals Roadmap (Pete)

- Soliciting those interested in [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html) goal
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip
- Soliciting those interested in [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html) goal
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip
