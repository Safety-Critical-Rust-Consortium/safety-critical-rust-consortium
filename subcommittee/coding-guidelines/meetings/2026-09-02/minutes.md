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
   - Parent tracking issue: [#575 Mapping for MISRA C++:2023 to Rust Guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)
   - Initial documentation PR: [#1226 Add the MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)
   - [Working spreadsheet](https://docs.google.com/spreadsheets/d/12e9Tr8PUTvVr87nUH0MQTwL31yU6YihQVxlvkqlo9SA/edit?gid=0#gid=0), currently reporting 179/179 guidelines analyzed
   - Reference: [MathWorks listing of MISRA C++:2023 rules and directives](https://www.mathworks.com/help/bugfinder/misra-cpp-2023-rules-and-directives.html)
   - Review history: [August 26 minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-08-26/minutes.md) and [August 28 minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-08-28/minutes.md)
   - The scopes below contain only mappings without review comments on PR #1226 as of September 1 and not recorded as reviewed in previous working sessions
   - Goal: confirm or revise each proposed Rust categorization and capture decisions and follow-up work in the tracking issue and PR
   - **Group A - mappings applicable to Rust in general**
     - Scope (15 mappings): Rules 0.0.1, 0.0.2, 0.1.1, 0.1.2, 0.2.1, 0.2.2, 0.2.3, and 0.2.4; Directives 0.3.1 and 0.3.2; Rule 5.7.1; Directive 5.7.2; and Rules 5.13.4, 8.0.1, and 28.6.1
     - Group:
       1. xx
   - **Group B - mappings additionally applicable in the presence of unsafe code**
     - Scope (15 mappings): Rules 6.2.1, 6.2.2, 6.5.1, and 6.5.2; Directive 15.8.1; and Rules 21.10.1, 21.10.2, 21.10.3, 22.4.1, 23.11.1, 24.5.2, 25.5.1, 25.5.2, 25.5.3, and 28.6.3
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

- [Mira's analysis of differences to MISRust](https://github.com/inkreasing/safety-critical-rust-coding-guidelines/blob/misrust/src/appendices/standards-matrices/differences-to-misrust.rst)
- [MISRust paper](https://arxiv.org/abs/2605.23490)
- [MISRust supporting artifacts](https://github.com/embedded-software-laboratory/MISRust)

Overview of [Safety-Critical Rust](https://rust-lang.github.io/rust-project-goals/2026/roadmap-safety-critical-rust.html) Rust Project Goals Roadmap (Pete)

- Soliciting those interested in [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html) goal
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip
- Soliciting those interested in [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html) goal
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip
