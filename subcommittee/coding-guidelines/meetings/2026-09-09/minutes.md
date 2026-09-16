# **Coding Guidelines Subcommittee Meeting on 2026-09-09 @ 1700 CEST / 1100 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-9-9&sln=11-12&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker  
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-09-02/minutes.md)  
3. Introduction of new members  
4. Working session: continue reviewing the MISRA C++:2023 to Rust coding guidelines mapping (Mira / Douglas)  
   - Parent tracking issue: [\#575 Mapping for MISRA C++:2023 to Rust Guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)  
   - Documentation PR: [\#1226 Add MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)  
   - [Working spreadsheet](https://docs.google.com/spreadsheets/d/12e9Tr8PUTvVr87nUH0MQTwL31yU6YihQVxlvkqlo9SA/edit?gid=0#gid=0), covering all 179 guidelines  
   - Reference: [MathWorks listing of MISRA C++:2023 rules and directives](https://www.mathworks.com/help/bugfinder/misra-cpp-2023-rules-and-directives.html)  
   - Goal: confirm or revise each proposed Rust categorization and capture decisions and follow-up work in the tracking issue and PR  
   - **Group A \- language features, comments, and expressions**  
     - Scope (15 mappings): Rules 4.1.2, 4.6.1, 5.0.1, and 5.7.1; Directive 5.7.2; and Rules 5.7.3, 5.13.1, 5.13.2, 5.13.3, 5.13.4, 5.13.5, 6.0.4, 6.7.1, 6.7.2, and 8.0.1  
     - Group:  
       1. Not enough member to support both groups (some people left early)  
   - **Group B \- lifetimes and standard-library APIs**  
     - Scope (15 mappings): Rules 6.8.1, 21.2.1, 21.2.4, 21.6.4, 21.10.2, 21.10.3, 22.4.1, 23.11.1, 24.5.1, 24.5.2, 25.5.1, 25.5.2, 25.5.3, 26.3.1, and 28.6.3  
     - Group:  
       1. All members who checked in  
5. Round table

   ## **Check-in area**

   **Please add your name, and an emoji that describes your day.**

- Douglas Deslauriers 🍵  
- Espen Albrektsen 🤖  
- Markus Hosch 🎮  
- Mira Baumann 💤  
- William Barsse  
- Christof Petig 🧵  
- Oreste Bernardi  

  **Notetaker:**

- Mira

  For tips on how we take notes in the Safety-Critical Rust Consortium, please see the [Meeting Notetaker Role](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/docs/notetaker-role.md) doc.

  ## **Housekeeping section**

- Document space: [coding-guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/tree/main/subcommittee/coding-guidelines)  
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)  
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)  
- [`contributor experience` view](https://github.com/orgs/rustfoundation/projects/1/views/4)  
- [`coding guideline` view](https://github.com/orgs/rustfoundation/projects/1/views/5)

  ## **Meeting Minutes**

- Previous meeting minutes accepted
- No new members
- We didn’t split up, as there weren’t enough people around. We started with the rules assigned to group B.
- Mapping review:
  - Discussion on the different object model of rust and C++. [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/changes\#r3970122951](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/changes#r3970122951)
  - [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/changes\#r3970145272](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/changes#r3970145272)
  - [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/changes\#r3970225912](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/changes#r3970225912)
  - [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/changes\#r3970237937](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/changes#r3970237937)
  - [decision] Discussions on the applicability of setjmp/longjmp, signals and locale rules. After discussion we agreed to say these FFI cases do not apply to rust at all. [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/changes\#r3970433619](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/changes#r3970433619)
  - Discussion on the difference between Rust and C++ Arc and shared\_ptr in regards to control block handling, which affects this API. [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/changes\#r3970496856](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/changes#r3970496856)
- Short discussion on unsafe macros

  ## **Material**

  Any material to read before the meeting should be included here.

  Overview of [Safety-Critical Rust](https://rust-lang.github.io/rust-project-goals/2026/roadmap-safety-critical-rust.html) Rust Project Goals Roadmap (Pete)

- Soliciting those interested in [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html); register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip.  
- Soliciting those interested in [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html); register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip.

