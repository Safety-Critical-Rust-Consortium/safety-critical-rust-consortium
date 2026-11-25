# **Coding Guidelines Subcommittee Meeting on 2026-11-25 @ 1600 CET / 1000 EST**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-11-25&sln=10-11&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-11-18/minutes.md)
3. Introduction of new members
4. Follow-up from the MISRA C++ mapping review
   - Continue [#1255](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1255), focusing on the new Directive 0.3.2 work:
     - [#1264](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1264): safe-callable functions that can cause undefined behavior must be `unsafe`.
     - [#1265](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1265): calls must satisfy documented contracts.
     - [#1266](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1266): unsafe blocks and unsafe functions must document their safety reasoning and contracts.
   - Work through the scope, examples, and next steps for these drafts.
5. FLS study group
   - Update on the first session and regular meeting schedule in the [Zulip discussion](https://rust-lang.zulipchat.org/#narrow/channel/579369-safety-critical-consortium.2Fcoding-guidelines/topic/FLS.20Study.20Group.20-.20updating.20guidelines).
6. Round table
   - Check in on the remaining follow-ons, including FFI scope, function-local statics, `Deref` coercions, `Clone`/`Drop`/`Pin`, and unintended copies.
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
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.org/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)
- [`contributor experience` view](https://github.com/orgs/rustfoundation/projects/1/views/4)
- [`coding guideline` view](https://github.com/orgs/rustfoundation/projects/1/views/5)

## **Meeting Minutes**

- xx

## **Material**

Meeting-specific reading:

- [November 18 meeting minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-11-18/minutes.md)
- [MISRA C++ mapping PR #1226](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)
- [#1255 Questions left from the mapping review](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1255)
- [#1264 Unsafe functions and soundness](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1264)
- [#1265 Documented function contracts](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1265)
- [#1266 Safety reasoning and contracts](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1266)
- [FLS Audit Guide](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/blob/main/docs/fls-audit.md)
