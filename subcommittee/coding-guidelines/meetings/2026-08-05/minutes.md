# **Coding Guidelines Subcommittee Meeting on 2026-08-05 @ 1600 CEST / 1100 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-8-5&sln=11-12&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker  
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-07-31/minutes.md)  
3. Introduction of new members  
4. Discuss the RustConf 2026 SCRC room (Pete)  
   - AdaCore is sponsoring the room on Monday  
   - Discuss plans for the room, including attendance and how the space will be used  
   - [Self-Nomination for Attendance to the SCRC Room](https://docs.google.com/spreadsheets/d/1QPpyOsrDQv_BQFlHLNfxUeT6dWaqicPtvX6T1U54CQI/edit?usp=sharing)  
   - Please enter your name if you would like to join the SCRC room at RustConf 2026  
5. Working session: continue reviewing the MISRA C++:2023 to Rust coding guidelines mapping (Mira / Pete)  
   - Parent tracking issue: [\#575 Mapping for MISRA C++:2023 to Rust Guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)  
   - Initial documentation PR: [\#1226 Add the MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)  
   - [Working spreadsheet](https://docs.google.com/spreadsheets/d/12e9Tr8PUTvVr87nUH0MQTwL31yU6YihQVxlvkqlo9SA/edit?gid=0#gid=0), currently reporting 179/179 guidelines analyzed  
   - Reference: [MathWorks listing of MISRA C++:2023 rules and directives](https://www.mathworks.com/help/bugfinder/misra-cpp-2023-rules-and-directives.html)  
   - Review history: [July 29 minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-07-29/minutes.md) and [July 31 minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-07-31/minutes.md)  
   - The July 31 session stopped at Rule 8.9.1; the scopes below contain only applicable mappings not yet reviewed in these working sessions  
   - Goal: confirm or revise each proposed Rust categorization and capture decisions and follow-up work in the tracking issue and PR  
   - **Group A \- expressions, control flow, types, and initialization**  
     - Scope (15 mappings): Rules 8.9.1, 8.14.1, 8.18.1, 8.20.1, 9.4.1, 9.4.2, 9.5.1, 10.1.1, 10.1.2, 10.2.1, 10.2.3, 10.4.1, 11.3.2, 11.6.1, and 12.3.1  
     - [https://meet.google.com/vwj-jitq-vpe](https://meet.google.com/vwj-jitq-vpe)  
     - Group:  
       1. Max Jacinto 👔  
       2. Markus Hosch 🫥  
       3. Samuel Wright 🛫  
       4. Espen Albrektsen 🙂  
       5. Jeongsoo Lee 🚀  
   - **Group B \- traits, object lifecycle, panics, and macros**  
     - Scope (15 mappings): Rules 13.3.3, 13.3.4, 14.1.1, 15.0.1, and 15.1.4; Directive 15.8.1; and Rules 16.6.1, 18.1.1, 18.4.1, 18.5.1, 18.5.2, 19.0.2, 19.0.3, 19.2.1, and 19.3.4  
     - [https://meet.google.com/xhx-yfmq-ped](https://meet.google.com/xhx-yfmq-ped)  
     - Group:  
       1. Pete LeVasseur 🏃  
       2. Oreste Bernardi 🫠  
       3. Mira Baumann 🎃  
       4. Michael Henn 🫩  
2. Round table

## **Check-in area**

- Espen Albrektsen 🙂  
- Oreste Bernardi 🫠  
- Max Jacinto 👔  
- Markus Hosch 🫥  
- Samuel Wright 🛫  
- Michael Henn 🫩  
- Pete LeVasseur 🏃  
- Mira Baumann 🎃  
- Jeongsoo Lee 🚀  

**Notetaker:**

- Max Jacinto

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

- \[10:05 AM\] Previous meeting minutes accepted  
- \[10:05 AM\] Introduction of new member, welcome\!  
  - [https://github.com/github/codeql-coding-standards](https://github.com/github/codeql-coding-standards) CodeQL Coding Standards project that aims to collab with/help the Consortium  
- \[10:08 AM\] Mapping of members that are going to RustConf  
- \[10:08 AM\] Walk-in items  
  - Discussion of how useful the comments left on the MISRA C++ PR were to gauge how things are done  
    - Comments were useful in the sense of measuring how strict categorization was  
- \[10:10 AM\] Working session  
  - Assignment of group members; ensure each group has at least one member that has access to the MISRA C++ guidelines  
  - \[10:14 AM\] Time to split\!  
- \[10:57 AM\] Back to the main room  
  - Proposal of review from other projects/teams (such as iceoryx2) regarding the use of unsafe to analyze their cases and review them for future OpSem team meeting

## **Material**

Any material to read before the meeting should be included here.

Overview of [Safety-Critical Rust](https://rust-lang.github.io/rust-project-goals/2026/roadmap-safety-critical-rust.html) Rust Project Goals Roadmap (Pete)

- Soliciting those interested in [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html) goal  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip  
- Soliciting those interested in [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html) goal  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip
