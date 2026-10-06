# **Coding Guidelines Subcommittee Meeting on 2026-09-30 @ 1700 CEST / 1100 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-9-30&sln=11-12&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker  
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-09-23/minutes.md)  
3. Introduction of new members  
4. Working session: continue reviewing the MISRA C++:2023 to Rust coding guidelines mapping  
   - Parent tracking issue: [\#575 Mapping for MISRA C++:2023 to Rust Guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)  
   - Documentation PR: [\#1226 Add MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)  
   - [Working spreadsheet](https://docs.google.com/spreadsheets/d/12e9Tr8PUTvVr87nUH0MQTwL31yU6YihQVxlvkqlo9SA/edit?gid=0#gid=0), covering all 179 guidelines  
   - Reference: [MathWorks listing of MISRA C++:2023 rules and directives](https://www.mathworks.com/help/bugfinder/misra-cpp-2023-rules-and-directives.html)  
   - Goal: confirm or revise each proposed Rust categorization and capture decisions and follow-up work in the tracking issue and inline comments on the PR  
   - *Please leave feedback inline on the relevant mapping in PR \#1226, including agreement with the proposed categorization.*  
   - **Group A \- type declarations, class hierarchies, and object operations**  
     - Scope (15 mappings): Rules 11.3.1, 11.6.3, 12.2.1, 12.2.2, 12.2.3, 13.1.1, 13.1.2, 13.3.1, 13.3.2, 15.0.2, 15.1.1, 15.1.2, 15.1.3, 15.1.5, and 16.5.2  
     - Group: TBD  
   - **Group B \- expressions, statements, and enumerations**  
     - Scope (15 mappings): Rules 8.0.1, 8.19.1, 9.2.1, 9.3.1, 9.5.2, 9.6.1, 9.6.2, 9.6.3, 9.6.4, 9.6.5, 10.0.1, 10.1.1, 10.2.2, 10.2.3, and 16.5.1  
     - Group: TBD  
5. Round table

   ## **Check-in area**

   **Please add your name, and an emoji that describes your day.**

- Douglas Deslauriers  
- Oreste Bernardi   
- Alex Celeste  
- Achim Kriso  
- Michael Henn 🍕  
- K. Wayne Lee 🤖

  **Notetaker:**

- Alex Celeste

  For tips on how we take notes in the Safety-Critical Rust Consortium, please see the [Meeting Notetaker Role](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/docs/notetaker-role.md) doc.

  ## **Housekeeping section**

- Document space: [coding-guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/tree/main/subcommittee/coding-guidelines)  
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)  
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)  
- [`contributor experience` view](https://github.com/orgs/rustfoundation/projects/1/views/4)  
- [`coding guideline` view](https://github.com/orgs/rustfoundation/projects/1/views/5)

  ## **Meeting Minutes**

- No new members, no objection to previous minutes  
-  Reviewing the MISRA C++ 2023 mapping:   
  - Notes for individual rule reviews added directly as comments on the PR  
  - in the absence of more people, handling group A all together:  
    - Some commentary might be needed about the antipatterns associated with implementing Deref in order to simulate inheritance.  
    - If RFC 1210 is moved to the main language an equivalent of 13.3.1 might become applicable  
    - Additionally a new rule needed to prevent misuse of \`Deref\` coercion.  
  - Moving to group B:  
    - The C++ and Rust operator set is similar *enough* to treat as applicable  
    - While not the subject of the rule, there is some overlap between \`\!\` and \`\[\[noreturn\]\]\` esp wrt coercion  
    - Possible new rule for imports of enumerators (?) which does *not* map to 10.2.2  
  - 10.2.3 caused some extended discussion  
  - We agreed with all proposed mappings in this group.  
- No other business.  
- Adjourned.

  ## **Material**

  Meeting-specific reading:

- [MISRA C++ mapping proposed in PR \#1226](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files)
