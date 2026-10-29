# **Coding Guidelines Subcommittee Asia Pacific + Americas Meeting on 2026-10-30 @ 0800 JST / 2026-10-29 @ 1900 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-10-29&sln=19-20&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-10-28/minutes.md)
3. Introduction of new members
4. FLS study group
   - Follow up on the participant call and arrange the first monthly session.
   - [Zulip discussion](https://rust-lang.zulipchat.com/#narrow/channel/579369-safety-critical-consortium.2Fcoding-guidelines/topic/FLS.20Study.20Group.20-.20updating.20guidelines/with/634982556).
   - Related issues: [#1237](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1237) and [#1240](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1240).
5. Working session: continue reviewing the MISRA C++:2023 to Rust coding guidelines mapping
   - Parent tracking issue: [#575 Mapping for MISRA C++:2023 to Rust Guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)
   - Documentation PR: [#1226 Add MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)
   - [Working spreadsheet](https://docs.google.com/spreadsheets/d/12e9Tr8PUTvVr87nUH0MQTwL31yU6YihQVxlvkqlo9SA/edit?gid=0#gid=0), covering all 179 guidelines
   - Reference: [MathWorks listing of MISRA C++:2023 rules and directives](https://www.mathworks.com/help/bugfinder/misra-cpp-2023-rules-and-directives.html)
   - Goal: confirm or revise each proposed Rust categorization and capture decisions and follow-up work in the tracking issue and inline comments on the PR.
   - *Please leave feedback inline on the relevant mapping in PR #1226, including agreement with the proposed categorization.*
   - **Single group**
     - Scope (6 mappings): Rules 19.3.5, 19.6.1, 21.2.2, 22.4.1, 28.6.1, and 30.0.1.
     - Continue after Rule 19.3.3. For Rules 22.4.1 and 28.6.1, confirm earlier outcomes or review the mapping, and record the outcome inline.
   - **Follow-up from existing reviews**
     - October 28: rationale edits for Rules 7.0.2, 19.1.3, 19.2.2, 19.2.3, and 19.3.1–19.3.3; move [Rule 19.3.1](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226#discussion_r4401938844) to applicable and simplify Rule 19.3.3 while retaining background as RST comments.
     - Decide whether rationales may delegate classification to MISRA C 2025 ADD6, including Rule 19.3.2 ([#1245](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1245)); document the agreed scope of stable features only ([#1243](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1243)).
     - Revisit [Rule 5.13.4 categorization](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226#discussion_r4340357217) and [Rule 6.7.1 and static variables](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226#discussion_r4346711516).
     - Remaining October 21 rationale edits for Rules 18.3.1, 18.3.2, 18.3.3, and 19.1.1.
6. Round table
   - Remaining work toward coding guidelines v0.2.0.

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

- [October 28 meeting minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-10-28/minutes.md)
- [MISRA C++ mapping proposed in PR #1226](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files)
- [FLS Audit Guide](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/blob/main/docs/fls-audit.md)
