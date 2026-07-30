# **Coding Guidelines Subcommittee Asia Pacific + Americas Meeting on 2026-07-31 @ 0800 JST / 1900 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-7-30&sln=19-20&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-07-29/minutes.md)
3. Introduction of new members
4. [RustConf 2026 - Self-Nomination for Attendance to SCRC Room](https://docs.google.com/spreadsheets/d/1QPpyOsrDQv_BQFlHLNfxUeT6dWaqicPtvX6T1U54CQI/edit?usp=sharing)
   - Please enter your self-nomination if you would like to join the SCRC room at RustConf 2026
5. Review [PR #1227: refine pointer conversion guidance](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1227) (Pete)
   - Context: [PR #1228](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1228) updated the FLS lock; PR #1227 is now a documentation-only follow-up
   - Review focus: pointer provenance wording, conversion-rule ownership, the focused function-pointer rule, and partial standards-matrix coverage
   - Goal: agree on the guideline split, the new rule's required category, the MISRA C:2025 R.11.1 partial mapping, and any category follow-up work
   - [Deploy preview](https://deploy-preview-1227--scrc-coding-guidelines.netlify.app)
6. Working session: continue reviewing the MISRA C++:2023 to Rust coding guidelines mapping (Mira / Pete)
   - Parent tracking issue: [#575 Mapping for MISRA C++:2023 to Rust Guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)
   - Initial documentation PR: [#1226 Add the MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)
   - [Working spreadsheet](https://docs.google.com/spreadsheets/d/12e9Tr8PUTvVr87nUH0MQTwL31yU6YihQVxlvkqlo9SA/edit?gid=0#gid=0), currently reporting 179/179 guidelines analyzed
   - Reference: [MathWorks listing of MISRA C++:2023 rules and directives](https://www.mathworks.com/help/bugfinder/misra-cpp-2023-rules-and-directives.html)
   - Goal: continue the initial mapping review, resolve remaining discussions, and capture decisions and follow-up work in the tracking issue and PR
   - Scope (15 mappings): Rules 6.0.3, 6.8.2, 6.8.3, 6.8.4, 7.0.1, 7.0.2, 7.0.4, 8.1.2, 8.7.1, 8.7.2, 8.9.1, 8.18.1, 8.20.1, 9.4.1, and 9.4.2
   - This carries forward the 13 mappings not reached on July 29 and adds Rules 9.4.1 and 9.4.2
7. Round table

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

Any material to read before the meeting should be included here.

Overview of [Safety-Critical Rust](https://rust-lang.github.io/rust-project-goals/2026/roadmap-safety-critical-rust.html) Rust Project Goals Roadmap (Pete)

- Soliciting those interested in [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html) goal
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip
- Soliciting those interested in [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html) goal
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip
