# **Coding Guidelines Subcommittee Meeting on 2026-09-16 @ 1700 CEST / 1100 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-9-16&sln=11-12&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker  
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-09-09/minutes.md)  
3. Introduction of new members  
4. Working session: continue reviewing the MISRA C++:2023 to Rust coding guidelines mapping (Mira)  
   - Parent tracking issue: [\#575 Mapping for MISRA C++:2023 to Rust Guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)  
   - Documentation PR: [\#1226 Add MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)  
   - [Working spreadsheet](https://docs.google.com/spreadsheets/d/12e9Tr8PUTvVr87nUH0MQTwL31yU6YihQVxlvkqlo9SA/edit?gid=0#gid=0), covering all 179 guidelines  
   - Reference: [MathWorks listing of MISRA C++:2023 rules and directives](https://www.mathworks.com/help/bugfinder/misra-cpp-2023-rules-and-directives.html)  
   - Goal: confirm or revise each proposed Rust categorization and capture decisions and follow-up work in the tracking issue and PR  
   - **Group A \- literals, declarations, and conversions**  
     - Scope (15 mappings): Rules 5.13.6, 5.13.7, 6.0.1, 6.0.2, 6.2.3, 6.2.4, 6.4.3, 6.9.1, 6.9.2, 7.0.3, 7.0.5, 7.0.6, 7.11.1, 7.11.2, and 7.11.3  
     - Meeting link: [https://meet.google.com/hki-ptve-str](https://meet.google.com/hki-ptve-str)  
     - Group: TBD  
   - **Group B \- expressions, statements, and enumerations**  
     - Scope (15 mappings): Rules 8.1.1, 8.3.1, 8.3.2, 8.18.2, 8.19.1, 9.2.1, 9.3.1, 9.5.2, 9.6.1, 9.6.2, 9.6.3, 9.6.4, 9.6.5, 10.0.1, and 10.2.2  
     - Meeting link: [https://meet.google.com/daf-zaqs-mhx](https://meet.google.com/daf-zaqs-mhx)  
     - Group: n/a  
5. Round table

   ## **Check-in area**

   **Please add your name, and an emoji that describes your day.**

- Sam Wright 🌧️  
- Danie Dia 🌇  
- Sam Kellam  
- Markus Hosch  

  **Notetaker:**

- Markus Hosch

  For tips on how we take notes in the Safety-Critical Rust Consortium, please see the [Meeting Notetaker Role](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/docs/notetaker-role.md) doc.

  ## **Housekeeping section**

- Document space: [coding-guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/tree/main/subcommittee/coding-guidelines)  
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)  
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)  
- [`contributor experience` view](https://github.com/orgs/rustfoundation/projects/1/views/4)  
- [`coding guideline` view](https://github.com/orgs/rustfoundation/projects/1/views/5)

  ## **Tasks**

- xx

  ## **Meeting Minutes**

- Acceptance of meeting minutes: accepted  
- New participant, but with technical issues → Next time  
- Working on rules:  
  - Agree on assessment of rule 5.13.6  
  - Agree on assessment of rule 5.13.7  
  - Agree on assessment of rule 6.0.1  
  - Agree on assessment of rule 6.0.2  
  - Agree on assessment of rule 6.2.3  
  - 6.2.4: extern “C” addressing two different C++ functions is a problem on the C++ side and not covered by the Rust coding guidelines. \#\[no\_mangle\] does affect unsafe Rust, but if the colliding definitions are in the same crate, the compiler will see it, otherwise the linker will catch it.  
  - Agree on assessment of rule 6.4.3  
  - Agree on assessment of rule 6.9.1. The trait case also does not apply because it’s not a redeclaration; the trait declaration is a constraint for the impl block, and this constraint is checked by the compiler.  
  - Agree mostly with 6,9,2. However, the same working applies to usize and size as in the MISRA C++ standard: Only use it if its pointer sized nature is sufficient.  
  - Agree on assessment of rule 7.0.3. Explicit conversion to/from u32 is fine as the intent of the developer is clearly stated.  
  - Agree on assessment of rule 7.0.5  
  - Agree on assessment of rule 7.0.6  
  - Rules from 7.11.1 and onward not covered   
    - due to time 7.11.1, 7.11.2, and 7.11.3

  ## **Material**

  Any material to read before the meeting should be included here.

  Overview of [Safety-Critical Rust](https://rust-lang.github.io/rust-project-goals/2026/roadmap-safety-critical-rust.html) Rust Project Goals Roadmap (Pete)

- Soliciting those interested in [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html); register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip.  
- Soliciting those interested in [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html); register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip.

