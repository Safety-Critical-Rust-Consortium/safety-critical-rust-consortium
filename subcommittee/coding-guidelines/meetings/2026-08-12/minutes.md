# **Coding Guidelines Subcommittee Meeting on 2026-08-12 @ 1600 CEST / 1100 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-8-12&sln=11-12&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker  
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-08-05/minutes.md)  
3. Introduction of new members  
4. Pete is on a work trip next week; who would like to run the meeting\!?  
5. Discuss the RustConf 2026 SCRC room (Pete)  
   - AdaCore is sponsoring the room on Monday  
   - Discuss plans for the room, including attendance and how the space will be used  
   - [Self-Nomination for Attendance to the SCRC Room](https://docs.google.com/spreadsheets/d/1QPpyOsrDQv_BQFlHLNfxUeT6dWaqicPtvX6T1U54CQI/edit?usp=sharing)  
   - Please enter your name if you would like to join the SCRC room at RustConf 2026  
6. Discuss proposal to periodically reconcile the coding guidelines with the FLS (Sam)  
   - Can find this on Zulip [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Update.20the.20FLS.20spec.20lock.20less.20often.3F/with/615890824)  
7. Update on Eclipse iceoryx2 `// Safety:` comments and Rust Abstract Machine narrative (Andreas Weis)  
   - In pursuit of the Rust Project Goal: [Normative Documentation for Sound `unsafe` Rust](https://rust-lang.github.io/goals/2026/safe-unsafe-for-safety-critical.html)  
   - Update on work to add `// Safety:` comments to iceoryx2's `unsafe` usages, citing normative Rust documentation where was possible and identifying gaps where it is not  
   - Update on the Rust Abstract Machine narrative for iceoryx2's shared-memory use cases  
   - Stand-alone examples are available here: [https://github.com/ekxide/iox2-scrc-examples](https://github.com/ekxide/iox2-scrc-examples)  
   - Goal: review progress and identify concrete questions or documentation gaps to take to the Rust Project Operational Semantics Team (t-opsem)  
   - Previous discussions: [May 26 t-opsem expert session](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/liaison/meetings/2026-05-26-opsem-expert-session/minutes.md) and [July 8 iceoryx2 examples walkthrough](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-07-08/minutes.md)  
8. Working session, if time: continue reviewing the MISRA C++:2023 to Rust coding guidelines mapping (Mira / Pete)  
   - Parent tracking issue: [\#575 Mapping for MISRA C++:2023 to Rust Guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)  
   - Initial documentation PR: [\#1226 Add the MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)  
   - [Working spreadsheet](https://docs.google.com/spreadsheets/d/12e9Tr8PUTvVr87nUH0MQTwL31yU6YihQVxlvkqlo9SA/edit?gid=0#gid=0), currently reporting 179/179 guidelines analyzed  
   - Reference: [MathWorks listing of MISRA C++:2023 rules and directives](https://www.mathworks.com/help/bugfinder/misra-cpp-2023-rules-and-directives.html)  
   - Review history: [August 5 minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-08-05/minutes.md)  
   - The August 5 groups reviewed through Rules 9.5.1 and 14.1.1, respectively; the scope below contains the next applicable mappings without review comments on the PR  
   - Scope (15 mappings): Rules 10.1.1, 10.1.2, 10.2.1, 10.2.3, 10.4.1, 11.3.2, 11.6.1, 12.3.1, 15.0.1, and 15.1.4; Directive 15.8.1; and Rules 16.6.1, 18.1.1, 18.4.1, and 18.5.1  
   - Goal: confirm or revise each proposed Rust categorization and capture decisions and follow-up work in the tracking issue and PR  
9. Round table

## **Check-in area**

- Daniel Dia 😀  
- Michael Henn ☕  
- Max Jacinto 👾  
- Pete LeVasseur 🥵  
- Jeongsoo Lee 🫩  
- Achim Kriso 🦆  
- Oreste Bernardi 🫠  
- Mira Baumann 🔍  
- Andreas Weis💻  
- Mark Hermeling (from :37) 🏃  
- Kangwon Lee 🤖

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

- Andreas: ask the opsem team about the current examples and story code.

## **Meeting Minutes**

- Meeting Notes accepted.  
- No new members.  
- Discussion of the proposed new FLS lock policy in the guidelines repo.  
- Presentation and discussion of the second iceoryx2 example and the proposed story code  
  - Story example 1 uncontroversial  
  - Story example 2 possible issue with atomics in the payload  
  - Story example 3 uncontroversial  
  - Mapping from POSIX to language semantics is unspecified  
  - Aliasing is the big issue  
- No time for MISRA C++ mapping review.

## **Material**

Any material to read before the meeting should be included here.

Overview of [Safety-Critical Rust](https://rust-lang.github.io/rust-project-goals/2026/roadmap-safety-critical-rust.html) Rust Project Goals Roadmap (Pete)

- Soliciting those interested in [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html) goal  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip  
- Soliciting those interested in [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html) goal  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip
