# **Coding Guidelines Subcommittee Meeting on 2026-10-07 @ 1700 CEST / 1100 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-10-7&sln=11-12&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker  
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-09-30/minutes.md)  
3. Introduction of new members  
4. Working session: continue reviewing the MISRA C++:2023 to Rust coding guidelines mapping  
   - Parent tracking issue: [\#575 Mapping for MISRA C++:2023 to Rust Guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)  
   - Documentation PR: [\#1226 Add MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)  
   - [Working spreadsheet](https://docs.google.com/spreadsheets/d/12e9Tr8PUTvVr87nUH0MQTwL31yU6YihQVxlvkqlo9SA/edit?gid=0#gid=0), covering all 179 guidelines  
   - Reference: [MathWorks listing of MISRA C++:2023 rules and directives](https://www.mathworks.com/help/bugfinder/misra-cpp-2023-rules-and-directives.html)  
   - Goal: confirm or revise each proposed Rust categorization and capture decisions and follow-up work in the tracking issue and inline comments on the PR  
   - *Please leave feedback inline on the relevant mapping in PR \#1226, including agreement with the proposed categorization.*  
   - **Group A \- templates, panic handling, and macros**  
     - Scope (15 mappings): Rules 17.8.1, 18.1.2, 18.3.1, 18.3.2, 18.3.3, 19.0.1, 19.0.4, 19.1.1, 19.1.2, 19.1.3, 19.2.2, 19.2.3, 19.3.1, 19.3.2, and 19.3.3  
     - Meeting link: [https\://meet.google.com/ekk-ahed-wia](https://meet.google.com/ekk-ahed-wia)  
     - Group: TBD  
   - **Group B \- language features, literals, and standard-library APIs**  
     - Scope (15 mappings): Rules 4.6.1 and 5.0.1; Directive 5.7.2; and Rules 5.7.3, 5.13.1, 5.13.2, 5.13.3, 5.13.4, 5.13.5, 24.5.1, 24.5.2, 26.3.1, 28.6.2, 28.6.3, and 30.0.2  
     - Meeting link: [https\://meet.google.com/puc-cndb-mgj](https://meet.google.com/puc-cndb-mgj)  
     - Group: TBD  
5. Round table

   ## **Check-in area**

   **Please add your name, and an emoji that describes your day.**

- Samuel Wright ☀️  
- Oreste Bernardi ⛰️  
- Mira Baumann 📝  
- Espen Albrektsen ➕  
- Achim Kriso 🦆  
- Kangwon Lee 🤖  
- xx  
- xx  
- xx  
- xx  
- xx  
- xx  
- xx

  **Notetaker:**

- Oreste Bernardi

  For tips on how we take notes in the Safety-Critical Rust Consortium, please see the [Meeting Notetaker Role](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/docs/notetaker-role.md) doc.

  ## **Housekeeping section**

- Document space: [coding-guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/tree/main/subcommittee/coding-guidelines)  
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)  
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)  
- [`contributor experience` view](https://github.com/orgs/rustfoundation/projects/1/views/4)  
- [`coding guideline` view](https://github.com/orgs/rustfoundation/projects/1/views/5)

  ## **Meeting Minutes**

- Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-09-30/minutes.md)  
  - Approved  
- No new members  
- Working session:  
  - We continue as single group due limited number of participants  
  - Reviewed group B  
- Mentioned the first Rust RFC coming from safety critical group [https\://github.com/rust-lang/rfcs/pull/4014](https://github.com/rust-lang/rfcs/pull/4014)  
- 

  ## **Material**

  Meeting-specific reading:

- [MISRA C++ mapping proposed in PR \#1226](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files)