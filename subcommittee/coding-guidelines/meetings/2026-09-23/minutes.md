# **Coding Guidelines Subcommittee Meeting on 2026-09-23 @ 1700 CEST / 1100 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-9-23&sln=11-12&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker  
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-09-16/minutes.md)  
3. Introduction of new members  
4. MISRA \<=\> CERT Mapping (David)  
5. CI change: no longer block PRs on changed FLS content, block release instead  
   - We use the FLS for traceability for guidelines  
   - But blocking contributions is unfortunate  
   - Idea \=\> block releases; form up group to once a month review the changes to the FLS and how they apply to the guidelines: [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1240](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1240)   
6. Working session: continue reviewing the MISRA C++:2023 to Rust coding guidelines mapping  
   - Parent tracking issue: [\#575 Mapping for MISRA C++:2023 to Rust Guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)  
   - Documentation PR: [\#1226 Add MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)  
     - Please leave comments inline on this pull request as it will make tracking feedback simpler.  
   - [Working spreadsheet](https://docs.google.com/spreadsheets/d/12e9Tr8PUTvVr87nUH0MQTwL31yU6YihQVxlvkqlo9SA/edit?gid=0#gid=0), covering all 179 guidelines  
   - Reference: [MathWorks listing of MISRA C++:2023 rules and directives](https://www.mathworks.com/help/bugfinder/misra-cpp-2023-rules-and-directives.html)  
   - Goal: confirm or revise each proposed Rust categorization and capture decisions and follow-up work in the tracking issue and inline comments on the PR  
   - **Group A \- pointers, arrays, and type declarations**  
     - Scope (15 mappings): Rules 7.11.1, 7.11.2, 7.11.3, 10.3.1, 11.3.1, 11.6.3, 12.2.1, 12.2.2, 12.2.3, 13.1.2, 13.3.1, 13.3.2, 15.0.2, 15.1.1, and 15.1.2  
     - Group:  
       1. Pete LeVasseur 👹  
       2. Kangwon Lee 🤖  
       3. Mira Baumann ⏰  
       4. Arthur Hicken 😐  
       5. Satoshi Kaneko  
   - **Group B \- expressions, statements, and enumerations**  
     - Scope (15 mappings): Rules 8.1.1, 8.3.1, 8.3.2, 8.18.2, 8.19.1, 9.2.1, 9.3.1, 9.5.2, 9.6.1, 9.6.2, 9.6.3, 9.6.4, 9.6.5, 10.0.1, and 10.2.2  
     - Group:  
       1. David Svoboda :-)  
       2. Max Jacinto 😵‍💫  
       3. Andrew Lynch 😴  
       4. Sam Wright  
7. Round table

   ## **Check-in area**

   **Please add your name, and an emoji that describes your day.**  
* Pete LeVasseur 👹  
* David Svoboda :-)  
* Kangwon Lee 🤖  
* Max Jacinto 😵‍💫  
* Mira Baumann ⏰  
* Andrew Lynch 😴  
* Arthur Hicken 😐  
* Sam Wright  
* Satoshi Kaneko  
* Xx

  **Notetaker:**

- Xx 

  For tips on how we take notes in the Safety-Critical Rust Consortium, please see the [Meeting Notetaker Role](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/docs/notetaker-role.md) doc.

  ## **Housekeeping section**

- Document space: [coding-guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/tree/main/subcommittee/coding-guidelines)  
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)  
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)  
- [`contributor experience` view](https://github.com/orgs/rustfoundation/projects/1/views/4)  
- [`coding guideline` view](https://github.com/orgs/rustfoundation/projects/1/views/5)

  ## **Meeting Minutes**

8. Solicitation of notetaker  
9. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-09-16/minutes.md)  
10. Introduction of new members  
11. MISRA \<=\> CERT Mapping (David)  
    - David presented a recent webinar about the CERT Fortran standard  
    - There was a request for a mapping between CERT C \<=\> MISRA C  
    - There are enough calls so that such a mapping has become an interesting priority  
12. CI change: no longer block PRs on changed FLS content, block release instead  
    - We use the FLS for traceability for guidelines  
    - But blocking contributions is unfortunate  
    - Idea \=\> block releases; form up group to once a month review the changes to the FLS and how they apply to the guidelines  
    - This is an O(n^2) problem, changes in the FLS can affect any subset of Rust rules.  We trust the community to suggest bugs/comments for this wrt CERT C.  
13. Working session: continue reviewing the MISRA C++:2023 to Rust coding guidelines mapping  
    - Parent tracking issue: [\#575 Mapping for MISRA C++:2023 to Rust Guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)  
    - Documentation PR: [\#1226 Add MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)  
    - [Working spreadsheet](https://docs.google.com/spreadsheets/d/12e9Tr8PUTvVr87nUH0MQTwL31yU6YihQVxlvkqlo9SA/edit?gid=0#gid=0), covering all 179 guidelines  
    - Reference: [MathWorks listing of MISRA C++:2023 rules and directives](https://www.mathworks.com/help/bugfinder/misra-cpp-2023-rules-and-directives.html)  
    - Goal: confirm or revise each proposed Rust categorization and capture decisions and follow-up work in the tracking issue and inline comments on the PR  
    - **Group A \- pointers, arrays, and type declarations**  
      - Scope (15 mappings): Rules 7.11.1, 7.11.2, 7.11.3, 10.3.1, 11.3.1, 11.6.3, 12.2.1, 12.2.2, 12.2.3, 13.1.2, 13.3.1, 13.3.2, 15.0.2, 15.1.1, and 15.1.2  
      - If you can write a bad bit of code, and it compiles, we need to rule for it.  
    - **Group B \- expressions, statements, and enumerations**  
      - Scope (15 mappings): Rules 8.1.1, 8.3.1, 8.3.2, 8.18.2, 8.19.1, 9.2.1, 9.3.1, 9.5.2, 9.6.1, 9.6.2, 9.6.3, 9.6.4, 9.6.5, 10.0.1, and 10.2.2  
      - 8.1.1 We agree that this rule doesn’t apply to safe rust, but without great certainty in our group.  We discussed if you can fake closures with an unsafe pointer, then rule 8.1.1 applies to Rust, but not otherwise.  
> > > > > > - New rule about using closures as intended?  
- 8.3.1 does not apply  
- 8.3.2 does not apply  
- 8.18.2 does not apply  
- 8.19.1 

	

-   
14. Round table

    ## **Material**

    Meeting-specific reading:

- [MISRA C++ mapping proposed in PR \#1226](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files)

  Overview of [Safety-Critical Rust](https://rust-lang.github.io/rust-project-goals/2026/roadmap-safety-critical-rust.html) Rust Project Goals Roadmap (Pete)

- Soliciting those interested in [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html); register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip.  
- Soliciting those interested in [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html); register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip.
