# **Coding Guidelines Subcommittee Asia Pacific \+ Americas Meeting on 2026-08-28 @ 0800 JST / 1900 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-8-27&sln=19-20&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker  
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-08-26/minutes.md)  
3. Introduction of new members  
4. Working session: continue reviewing the MISRA C++:2023 to Rust coding guidelines mapping (Mira / Pete)  
   - Parent tracking issue: [\#575 Mapping for MISRA C++:2023 to Rust Guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)  
   - Initial documentation PR: [\#1226 Add the MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)  
   - [Working spreadsheet](https://docs.google.com/spreadsheets/d/12e9Tr8PUTvVr87nUH0MQTwL31yU6YihQVxlvkqlo9SA/edit?gid=0#gid=0), currently reporting 179/179 guidelines analyzed  
   - Reference: [MathWorks listing of MISRA C++:2023 rules and directives](https://www.mathworks.com/help/bugfinder/misra-cpp-2023-rules-and-directives.html)  
   - Review history: [August 26 minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-08-26/minutes.md)  
   - Goal: confirm or revise each proposed Rust categorization and capture decisions and follow-up work in the tracking issue and PR  
   - **Single group**  
     - Scope (16 mappings): Rules 21.6.1, 21.6.2, 21.6.3, 22.3.1, 28.3.1, 28.6.1, and 28.6.4; Directive 15.8.1; and Rules 18.1.1, 21.6.5, 21.10.1, 21.10.2, 21.10.3, 22.4.1, 23.11.1, and 24.5.2  
5. Round table

   ## **Check-in area**

- Mikhail Antoshkin 👊🌧️  
- Pete LeVasseur 👋🌊  
- Max Jacinto 🤒

  **Notetaker:**

- Mikhail Antoshkin / Pete LeVasseur

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

- Continue review of MISRA C++   
- PR created related to adding a “reasoning” section in the style guidelines: https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1238


  ## **Material**

  Any material to read before the meeting should be included here.

  Overview of [Safety-Critical Rust](https://rust-lang.github.io/rust-project-goals/2026/roadmap-safety-critical-rust.html) Rust Project Goals Roadmap (Pete)

- Soliciting those interested in [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html) goal  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip  
- Soliciting those interested in [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html) goal  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip

