# **Coding Guidelines Subcommittee Meeting on 2026-07-29 @ 1600 CEST / 1100 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-7-29&sln=11-12&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-07-22/minutes.md)
3. Introduction of new members
4. [RustConf 2026 \- Self-Nomination for Attendance to SCRC Room](https://docs.google.com/spreadsheets/d/1QPpyOsrDQv_BQFlHLNfxUeT6dWaqicPtvX6T1U54CQI/edit?usp=sharing)
   - Please enter your self-nomination if you would like to join the SCRC room at RustConf 2026
5. Review [PR \#1227: refine pointer conversion guidance](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1227) (Pete)
   - Context: [PR \#1228](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1228) updated the FLS lock; PR \#1227 is now a documentation-only follow-up
   - Review focus: pointer provenance wording, conversion-rule ownership, the focused function-pointer rule, and partial standards-matrix coverage
   - Goal: agree on the guideline split, the new rule's required category, the MISRA C:2025 R.11.1 partial mapping, and any category follow-up work
   - [Deploy preview](https://deploy-preview-1227--scrc-coding-guidelines.netlify.app)
6. Working session: review progress on the MISRA C++:2023 to Rust coding guidelines mapping (Mira / Pete)
   - Parent tracking issue: [\#575 Mapping for MISRA C++:2023 to Rust Guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)
   - Initial documentation PR: [\#1226 Add the MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)
   - [Working spreadsheet](https://docs.google.com/spreadsheets/d/12e9Tr8PUTvVr87nUH0MQTwL31yU6YihQVxlvkqlo9SA/edit?gid=0#gid=0), currently reporting 179/179 guidelines analyzed
   - Reference: [MathWorks listing of MISRA C++:2023 rules and directives](https://www.mathworks.com/help/bugfinder/misra-cpp-2023-rules-and-directives.html)
   - Goal: review the initial mapping, resolve remaining discussions, and capture decisions and follow-up work in the tracking issue and PR
   - **Group A \- language validity, linkage, lifetimes, and conversions**
     - Scope (15 mappings): Rules 4.1.1, 4.1.2, 4.1.3, 6.0.4, 6.4.2, 6.7.1, 6.7.2, 6.8.1, 6.8.2, 6.8.3, 6.8.4, 7.0.1, 7.0.2, 7.0.4, and 8.1.2
     - Group:
       1. Mira Baumann 🌚
       2. Pete LeVasseur 🍿
       3. Douglas Deslauriers 🌿
       4. Matthew Butler
       5. Christof Petig 🛫🌋
   - **Group B \- casts, pointer operations, and expression behavior**
     - Scope (15 mappings): **Rules 8.2.1, 8.2.2, 8.2.3, 8.2.4, 8.2.5, 8.2.6, 8.2.7, 8.2.8, 8.2.10, 8.2.11,** 8.7.1, 8.7.2, 8.9.1, 8.18.1, and 8.20.1
     - Group:
       1. Achim Kriso 🦆
       2. Mark Hermeling (AdaCore) 🕺
       3. Max Jacinto 😵‍💫
       4. William Barsse
       5. David Svoboda :-)
       6. Kangwon Lee 🤖
7. Round table

## **Check-in area**

- Mira Baumann 🌚
- Pete LeVasseur 🍿
- Douglas Deslauriers 🌿
- Matthew Butler
- Christof Petig 🛫🌋
- Mark Hermeling (AdaCore) 🕺
- Max Jacinto 😵‍💫
- William Barsse
- David Svoboda :-)
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

- None

## **Meeting Minutes**

- Previous Week’s Meeting Minutes
  - Accepted without objection
- Introduction of New Members
  - Mark Hermeling was introduced
- RustConf
  - AdaCore has sponsored our room on Monday
  - If you are attending, please fill out your name on the [Google Sheet](https://docs.google.com/spreadsheets/d/1QPpyOsrDQv_BQFlHLNfxUeT6dWaqicPtvX6T1U54CQI/edit?usp=sharing)
  - It will be a lottery system, so if the limited space is filled, then names will be chosen
- [PR \#1227](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1227)
  - More care should be taken when updating the FLS spec to ensure it doesn’t affect existing rules
  - Please review these changes in this PR for accuracy
- CERT C Mapping
  - It seems we are about at the end of the road for these mappings
  - Thanks to everyone for the work
- MISRA C++ Mapping
  - Work has been done for on a [Google Sheet](https://docs.google.com/spreadsheets/d/12e9Tr8PUTvVr87nUH0MQTwL31yU6YihQVxlvkqlo9SA/edit?gid=0#gid=0)
  - Some recent Rust updates have actually changed applicability of some rules, such as variadic functions
  - There is a draft Pull Request [\#1226](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226) available to bring the mappings into our guidelines
  - Online versions of the MISRA C++ headline text is available on [some websites](https://docs.adacore.com/live/wave/codesonar_manual/html/codesonar_manual/CodeSonar.html#t=WarningClasses%2FMISRA_CPP.html)
  - The applicability for the Rules was done in a conservative manner, so even if a niche edge case appears in Rust, then it was marked as applicable
- MISRA C++ Working Session
  - Notes taken were posted to the PR, [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226\#pullrequestreview-4810108356](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226#pullrequestreview-4810108356)
  - [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)
  - Future work will be done to review the rest of these mappings
- Round Table
  - Feedback requested for the “Rust Specific Failure Modes” PR, [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1224](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1224)

## **Material**

Any material to read before the meeting should be included here.

Overview of [Safety-Critical Rust](https://rust-lang.github.io/rust-project-goals/2026/roadmap-safety-critical-rust.html) Rust Project Goals Roadmap (Pete)

- Soliciting those interested in [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html) goal
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip
- Soliciting those interested in [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html) goal
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip

