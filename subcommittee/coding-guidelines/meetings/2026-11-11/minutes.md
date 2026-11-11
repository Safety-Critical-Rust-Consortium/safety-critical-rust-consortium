# **Coding Guidelines Subcommittee Meeting on 2026-11-11 @ 1600 CET / 1000 EST**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-11-11&sln=10-11&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-11-04/minutes.md)
3. Introduction of new members
4. Mira: walkthrough of recent MISRA C++ mapping changes
   - Mira will walk through her recent changes in [PR #1226](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226), including the new Rust rationales for Rules 0.1.1 and 0.2.1.
   - Questions and discussion—for example, how destructors affect whether a variable counts as used, and which C++ exceptions carry over to Rust.
5. FLS study group
   - Update on availability in the LettuceMeet linked in the [Zulip discussion](https://rust-lang.zulipchat.com/#narrow/channel/579369-safety-critical-consortium.2Fcoding-guidelines/topic/FLS.20Study.20Group.20-.20updating.20guidelines/with/634982556) and scheduling the first session.
6. Working session: close out the MISRA C++:2023 to Rust mapping review
   - Parent tracking issue: [#575](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)
   - Documentation PR: [#1226 Add MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)
   - Continue from the [November 4 decision in #1245](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1245#issuecomment-6635417192): retain external rationales for now, work toward our own Rust-specific rationales, and do not block the release solely on that rewrite.
   - Continue the equivalence checks for **4.1.3, 5.7.1, Directive 5.7.2, 5.7.3, 6.0.2, 6.2.2, 6.4.1, and 19.3.1**, carrying over any November 4 outcomes not yet recorded inline. Capture whether each reference is sufficient for this release or a Rust-specific explanation is needed now.
     - Start with [4.1.3](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226#discussion_r3675832409), including its classification and the dependency from Rule 8.7.1.
   - If time permits, resolve [6.7.1](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226#discussion_r4350264105): should the restriction on persistent function-local state include safe atomics and locks?
   - Please leave feedback inline on the relevant mapping in PR #1226, including agreement with the proposed categorization and any required rationale changes.
7. Round table
   - Next working sessions: prepared batches of outstanding classifications and rationales, followed by FFI consistency across the standards appendices or trial reviews of existing draft guidelines before the incoming package.
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

- [November 4 meeting minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-11-04/minutes.md)
- [November 4 rationale decision in #1245](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1245#issuecomment-6635417192)
- [MISRA C++ mapping proposed in PR #1226](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files)
- [MISRA C:2025 Addendum 6](https://misra.org.uk/app/uploads/2025/03/MISRA-C-2025-ADD6.pdf) and [our MISRA C mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/blob/main/src/appendices/standards-matrices/misra-c-2025-mapping.rst)
- [FLS Audit Guide](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/blob/main/docs/fls-audit.md)
