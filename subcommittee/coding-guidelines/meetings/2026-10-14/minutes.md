# **Coding Guidelines Subcommittee Meeting on 2026-10-14 @ 1400 CEST / 1000 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-10-14&sln=11-12&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker  
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-10-07/minutes.md) (Accepted. No-inline comments.)  
3. Introduction of new members (No new members)  
4. Confirm outstanding review records from previous meetings  
   - Went over to the rules reviews during the last two meetings to make sure the discussion results were interpreted correctly. PR\#1226 [changes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/changes) included comments from September 30th.  
   - Recover missing outcomes for Rules 4.1.2, 5.7.1, 6.0.4, 6.4.2, 6.7.1, and 6.7.2 from July 29; Rule 7.0.2 from July 31 \<= Pete will handle this separately  
     - Rule 4.1.2: Agreed (deprecated features not to be used)  
     - Rule 5.7.1 :   
     - Question raised: on the remaining tasks before the guideline can be published  
     - Rule 6.0.4 : bucketed under unsafe. See also Rule 6.2.1 (One definition rule)  
     - [Rule 6.4.2](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/changes#r4272295581) : will consider stable features only (Will open a new Issue)  
     - Rule 6.7.1 : Applies. Currently Rust allows defining a static local variable in Rust yet MISRA C++ prohibits ([Playground link](https://play.rust-lang.org/?version=stable&mode=debug&edition=2024&gist=ae93d125ceb6fcdc88f7f1ae681ed236)) (See also 6.7.2)   
     - Rule 6.7.2 : \`static\` may have a variety of meanings in both C++ and Rust (Will open a new Issue)  
     - Rule 7.0.2 : Agree with the rationale but recommends some edits  
   - Rules 12.2.2 and 12.2.3 from September 30  
     - [https\://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-09-30/minutes.md](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-09-30/minutes.md)  
   - Recover the individual outcomes for the 15 mappings reviewed by October 7's Group B.  
     - [https\://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-10-07/minutes.md](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-10-07/minutes.md)   
     - Scope (15 mappings): Rules 4.6.1 and 5.0.1; Directive 5.7.2; and Rules 5.7.3, 5.13.1, 5.13.2, 5.13.3, 5.13.4, 5.13.5, 24.5.1, 24.5.2, 26.3.1, 28.6.2, 28.6.3, and 30.0.2  
   - Confirm whether Rules 22.4.1 and 28.6.1 were reached in earlier sessions.  
   - Record confirmed outcomes inline on PR \#1226. If an outcome cannot be recovered, identify the mapping for a future review; do not assume agreement.  
5. Working session: continue reviewing the MISRA C++:2023 to Rust coding guidelines mapping  
   - Parent tracking issue: [\#575 Mapping for MISRA C++:2023 to Rust Guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)  
   - Documentation PR: [\#1226 Add MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)  
   - [Working spreadsheet](https://docs.google.com/spreadsheets/d/12e9Tr8PUTvVr87nUH0MQTwL31yU6YihQVxlvkqlo9SA/edit?gid=0#gid=0), covering all 179 guidelines  
   - Reference: [MathWorks listing of MISRA C++:2023 rules and directives](https://www.mathworks.com/help/bugfinder/misra-cpp-2023-rules-and-directives.html)  
   - Scope: mappings without rule-specific PR feedback or a recorded completed review, following reconciliation against previous meeting notes.  
   - Goal: confirm or revise each proposed Rust categorization and capture decisions and follow-up work.  
   - *Please leave feedback inline on the relevant mapping in PR \#1226, including agreement with the proposed categorization.*  
   - **Group A \- templates, panic handling, and conditional compilation**  
     - Scope (10 mappings): Rules 17.8.1, 18.1.2, 18.3.1, 18.3.2, 18.3.3, 19.0.1, 19.0.4, 19.1.1, 19.1.2, and 19.1.3.  
     - Group: TBD  
   - **Group B \- file inclusion, macro expansion, and standard-library APIs**  
     - Scope (9 mappings): Rules 19.2.2, 19.2.3, 19.3.1, 19.3.2, 19.3.3, 19.3.5, 19.6.1, 21.2.2, and 30.0.1.  
     - Group: TBD  
   - If attendance favors a single group, work through Group A first, then Group B as time permits.  
6. Round table

## **Check-in area**

**Please add your name, and an emoji that describes your day.**

- Pete LeVasseur 👹  
- K. Wayne Lee 🤖  
- Satoshi Kaneko 😀  
- Jeongsoo Lee ⏰  
- Achim Kriso 🦆  
- Christof Petig

**Notetaker:**

- K. Wayne Lee 🤖

  For tips on how we take notes in the Safety-Critical Rust Consortium, please see the [Meeting Notetaker Role](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/docs/notetaker-role.md) doc.

## **Housekeeping section**

- Document space: [coding-guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/tree/main/subcommittee/coding-guidelines)  
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)  
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)  
- [`contributor experience` view](https://github.com/orgs/rustfoundation/projects/1/views/4)  
- [`coding guideline` view](https://github.com/orgs/rustfoundation/projects/1/views/5)

## **Meeting Minutes**

- Question to us as a group:  
  - Where can I find an overview of the tasks required to publish coding guideline v1.0 and the current progress? (I can only see a bunch of GitHub issues)  
  - I’m not clear on what remains to be done before the release or how much progress has been made so far. To be honest I didn't join the weekly meeting frequently and it might be the reason.

## **Material**

Meeting-specific reading:
  - [MISRA C++ mapping proposed in PR \#1226](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files)
