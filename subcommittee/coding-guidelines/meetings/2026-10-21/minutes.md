# **Coding Guidelines Subcommittee Meeting on 2026-10-21 @ 1600 CEST / 1000 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-10-21&sln=10-11&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-10-14/minutes.md)
3. Introduction of new members
4. FLS study group
   - Solicit participants to review changes in the FLS and reconcile drift with the coding guidelines.
   - Discuss a monthly cadence and arrange the first session.
   - Related issues: [#1237 Define process for when a guideline is affected by an FLS update](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1237) and [#1240 FLS audit: spec.lock drift](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1240).
5. Working session: continue reviewing the MISRA C++:2023 to Rust coding guidelines mapping
   - Parent tracking issue: [#575 Mapping for MISRA C++:2023 to Rust Guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)
   - Documentation PR: [#1226 Add MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)
   - [Working spreadsheet](https://docs.google.com/spreadsheets/d/12e9Tr8PUTvVr87nUH0MQTwL31yU6YihQVxlvkqlo9SA/edit?gid=0#gid=0), covering all 179 guidelines
   - Reference: [MathWorks listing of MISRA C++:2023 rules and directives](https://www.mathworks.com/help/bugfinder/misra-cpp-2023-rules-and-directives.html)
   - Goal: confirm or revise each proposed Rust categorization and capture decisions and follow-up work in the tracking issue and inline comments on the PR.
   - *Please leave feedback inline on the relevant mapping in PR #1226, including agreement with the proposed categorization.*
   - **Group A - confirm earlier review outcomes**
     - Scope (18 mappings): Rules 4.6.1 and 5.0.1; Directive 5.7.2; and Rules 5.7.3, 5.13.1, 5.13.2, 5.13.3, 5.13.4, 5.13.5, 7.0.2, 22.4.1, 24.5.1, 24.5.2, 26.3.1, 28.6.1, 28.6.2, 28.6.3, and 30.0.2.
     - Continue the review started on October 14 and record the individual outcomes inline. Review any mapping whose earlier outcome cannot be established, including Rules 22.4.1 and 28.6.1, whose review status remains uncertain.
     - Group: TBD
   - **Group B - templates, panic handling, macros, and standard-library APIs**
     - Scope (19 mappings): Rules 17.8.1, 18.1.2, 18.3.1, 18.3.2, 18.3.3, 19.0.1, 19.0.4, 19.1.1, 19.1.2, 19.1.3, 19.2.2, 19.2.3, 19.3.1, 19.3.2, 19.3.3, 19.3.5, 19.6.1, 21.2.2, and 30.0.1.
     - No rule-specific feedback or completed review found.
     - Group: TBD
6. Round table
   - Overview of remaining work toward coding guidelines v1.0 (follow-up from October 14).

## **Check-in area**

**Please add your name, and an emoji that describes your day.**

- xx
- xx
- xx
- xx
- xx
- xx
- xx
- xx
- xx
- xx
- xx
- xx
- xx

**Notetaker:**

- xx

For tips on how we take notes in the Safety-Critical Rust Consortium, please see the [Meeting Notetaker Role](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/docs/notetaker-role.md) doc.

## **Housekeeping section**

- Document space: [coding-guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/tree/main/subcommittee/coding-guidelines)
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)
- [`contributor experience` view](https://github.com/orgs/rustfoundation/projects/1/views/4)
- [`coding guideline` view](https://github.com/orgs/rustfoundation/projects/1/views/5)

## **Meeting Minutes**

- xx

## **Material**

Meeting-specific reading:

- [October 7 meeting minutes and Group B scope](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-10-07/minutes.md)
- [MISRA C++ mapping proposed in PR #1226](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files)
- [FLS Audit Guide](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/blob/main/docs/fls-audit.md)
