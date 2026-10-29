# **Coding Guidelines Subcommittee Meeting on 2026-10-28 @ 1500 CET / 1000 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-10-28&sln=10-11&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-10-21/minutes.md)
3. Introduction of new members
4. FLS study group
   - Follow up on the participant call and arrange the first monthly session.
   - Related issues: [#1237](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1237) and [#1240](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1240).
   - [Link](https://rust-lang.zulipchat.com/#narrow/channel/579369-safety-critical-consortium.2Fcoding-guidelines/topic/FLS.20Study.20Group.20-.20updating.20guidelines/with/634982556) to the Zulip thread where this is discussed. Pete will drop a link to a LettuceMeet here, so list your interest there if you’ve got it.
5. Working session: continue reviewing the MISRA C++:2023 to Rust coding guidelines mapping
   - Parent tracking issue: [#575 Mapping for MISRA C++:2023 to Rust Guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)
   - Documentation PR: [#1226 Add MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)
   - [Working spreadsheet](https://docs.google.com/spreadsheets/d/12e9Tr8PUTvVr87nUH0MQTwL31yU6YihQVxlvkqlo9SA/edit?gid=0#gid=0), covering all 179 guidelines
   - Reference: [MathWorks listing of MISRA C++:2023 rules and directives](https://www.mathworks.com/help/bugfinder/misra-cpp-2023-rules-and-directives.html)
   - Goal: confirm or revise each proposed Rust categorization and capture decisions and follow-up work in the tracking issue and inline comments on the PR.
   - *Please leave feedback inline on the relevant mapping in PR #1226, including agreement with the proposed categorization.*
   - **Single group**
     - Scope (14 mappings): Rules 7.0.2, 19.1.2, 19.1.3, 19.2.2, 19.2.3, 19.3.1, 19.3.2, 19.3.3, (we ended here) 19.3.5, 19.6.1, 21.2.2, 22.4.1, 28.6.1, and 30.0.1.
     - For Rules 7.0.2, 22.4.1, and 28.6.1, confirm earlier outcomes or review the mapping, and record the outcome inline.
   - Follow-up from existing reviews: [Rule 5.13.4 categorization](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226#discussion_r4340357217), [Rule 6.7.1 and static variables](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226#discussion_r4346711516), and the rationale edits requested on October 21.
6. Round table
   - Remaining work toward coding guidelines v0.2.0.

## **Check-in area**

**Please add your name, and an emoji that describes your day.**

- Michael Henn 🐘
- Pete LeVasseur 🖖
- Samuel Wright 🕶️
- K Wayne Lee 🤖
- Douglas Deslauriers 🐁
- Achim Kriso 🦆
- Jeongsoo Lee 👋
- Mira Baumann 🍎

**Notetaker:**

- K Wayne Lee 🤖

For tips on how we take notes in the Safety-Critical Rust Consortium, please see the [Meeting Notetaker Role](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/docs/notetaker-role.md) doc.

## **Housekeeping section**

- Document space: [coding-guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/tree/main/subcommittee/coding-guidelines)
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)
- [`contributor experience` view](https://github.com/orgs/rustfoundation/projects/1/views/4)
- [`coding guideline` view](https://github.com/orgs/rustfoundation/projects/1/views/5)

## **Meeting Minutes**

- FLS : Importance of traceability in regulated industries such as automotive
  - Representation of language and compiler
  - Deploy new coding guidelines blocked if not in sync with FLS
  - Hence would like the Guideline to be in sync with FLS.
  - Proposing a study group
  - Once a month. About an hour.
    - Guidelines up to date with FLS
    - Invitation is open
    - Link in Zulip (exact link?)
- Walk-in
  - Wayne organized a workshop at IEEE conference related to Rust
    - [https://compiler-safety-its.github.io/itsc-2026-workshop/](https://compiler-safety-its.github.io/itsc-2026-workshop/)
    - Co-organizer of the workshop expressed interest in participating as an observer in the SCRC.
-  7.0.2
  - Generally agreed
  - However, the final sentence should be changed to remove the suggestion.
- 19.1.2
  - Generally agree with the rationale
- 19.1.3
  - Rationale should be more general and talk about compiler errors instead of the specific value 0.
  - Agreed
- 19.2.2
  - Agreed
  - `give` of line 859 should be `given`
- 19.2.3
  - In the Coding Guidelines, consider replacing the link to the playground with a sample source code
  - agreed
- 19.3.1
  - Remove double negatives of `not recommend to not rely on`
  - Applicable here after removing double negative
- 19.3.2
  - Editorially the rationale should look similar to the previous rule's rationale.
  - Open question whether we want to keep to allow rationales delegated to other documents, like MISRA C 2025 in this case.
  - Possibly a communication channel with MISRA can be desirable
  - Need make the rationalization more robust
- 19.3.3
  - Currently listed under not-applicable
  - Paste macro is a workaround
  - As compiler error will filter out we can remove the bullet points and state not-applicable
  - Every line of code can be a burden.
  - Maintaining two documents? One public Guideline and one todo-list.
    - Additional context
- Possibly we can finish next week
- Pete may not be running the meeting next week. Douglas will fill in
- MISRA C++ pdf of today’s meeting was out of date.

## **Material**

Meeting-specific reading:

- [October 21 meeting minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-10-21/minutes.md)
- [MISRA C++ mapping proposed in PR #1226](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files)
- [FLS Audit Guide](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/blob/main/docs/fls-audit.md)
