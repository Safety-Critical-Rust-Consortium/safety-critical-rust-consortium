# **Coding Guidelines Subcommittee Meeting on 2026-11-18 @ 1600 CET / 1000 EST**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-11-18&sln=10-11&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-11-11/minutes.md)
3. Introduction of new members
4. FLS study group
   - Met on Nov 13, 2026 with Mira and David Svoboda, resolved outstanding `spec.lock` differences with upstream FLS.
   - We plan to continue to resolve these things async as they come up and meet monthly.
   - If you’d like to get involved watch this [Zulip discussion](https://rust-lang.zulipchat.com/#narrow/channel/579369-safety-critical-consortium.2Fcoding-guidelines/topic/FLS.20Study.20Group.20-.20updating.20guidelines/with/634982556) for scheduling
5. MISRA C++ mapping release update and celebration
   - Celebrate [PR #1226](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226) landing in the release
   - Now live on the website 🎉
     - [https://coding-guidelines.arewesafetycriticalyet.org/appendices/standards-matrices/misra-cpp-2023-mapping.html](https://coding-guidelines.arewesafetycriticalyet.org/appendices/standards-matrices/misra-cpp-2023-mapping.html)
6. Follow-on issues from the MISRA C++ mapping
   - Start with the three cross-cutting issues most likely to shape the next round of work:
     - [#1255 Questions left from the mapping review](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1255)
     - [#1256 FFI scope in the standards mappings](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1256)
     - [#1257 Function-local statics](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1257)
   - Decide what to take up first. Keep the remaining follow-ons for later discussion, including `Deref` coercions, `Clone`/`Drop`/`Pin`, and unintended copies.
7. Round table

## **Check-in area**

**Please add your name, and an emoji that describes your day.**

- Pete LeVasseur 😹
- Mario Mottl 🚀
- Jeongsoo Lee :D
- Mira Baumann 🧭
- Max Jacinto 🫠

**Notetaker:**

- Mario Mottl

For tips on how we take notes in the Safety-Critical Rust Consortium, please see the [Meeting Notetaker Role](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/docs/notetaker-role.md) doc.

## **Housekeeping section**

- Document space: [coding-guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/tree/main/subcommittee/coding-guidelines)
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.org/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)
- [`contributor experience` view](https://github.com/orgs/rustfoundation/projects/1/views/4)
- [`coding guideline` view](https://github.com/orgs/rustfoundation/projects/1/views/5)

## **Meeting Minutes**

- No rejection of last week's Meeting Minutes.
- No new members
- FLS Study Group:
  - Outstanding spec\<dot\>rs difference will be resolved mostly asynchronously
- Celebration of [PR #1226](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226) landing.
  See: [https://coding-guidelines.arewesafetycriticalyet.org/appendices/standards-matrices/misra-cpp-2023-mapping.html](https://coding-guidelines.arewesafetycriticalyet.org/appendices/standards-matrices/misra-cpp-2023-mapping.html)
- [#1255 Questions left from the mapping review](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1255)
  - (Some links could be broken because of a GitHub Bug/Issue)
  - [0.3.2](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226#discussion_r3916045401) “ A function call shall not violate the function’s precondition”
    - [todo] An issue should be opened that `safe` code shall not invoke undefined-behaviour / unsound behaviour. \<insert issue link\>
      1. Proposed split into two guidelines for `safe` and `unsafe`
  - [5.10.1](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226#discussion_r3959464507) “User-defined identifiers shall have an appropriate form”
    - With the new rational this will be marked as `non-applicable`
      1. The comment about “_” at the start of an identifier disabling the linter warning will be left inside the rationale
  - [6.0.4](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226#discussion_r4272252019) “The identifier `main` shall not be used for a function other than the global function `main` ”
    - Related to 6.2.1 “ The one-definition rule shall not be violated”
    - Another extern “C”  example should be given.
      1. [todo] An issue should be opened about aligning on this issue. \<insert issue link\>
  - [6.9.2](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226#discussion_r4079767090) "The names of the standard signed integer types and standard unsigned integer types should not be used”
    - C++ Reference: Cppreference [“Fixed width integer types”](https://en.cppreference.com/cpp/types/integer)
    - Comparison between (C++)`std::uintptr_t && std::intptr_t` and (Rust)`usize && isize`
      1. `isize && usize` are strongly enough defined by the language for every platform to make this rule not applicable for Rust
    - Mentioned rust docs about `isize && usize`: [Numeric types](https://doc.rust-lang.org/reference/types/numeric.html#r-type.numeric.int.size.usize) ( not relevant )
- [#1256 FFI scope in the standards mappings](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1256)
  - Not discussed
- [#1257 Function-local statics](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1257)
  - Not discussed
- Review the C++ Misra Mappings and replacing links to point to the FLS-Spec
  - [todo] An issue should be opened about this \<insert issue link\>.

## **Material**

Meeting-specific reading:

- [November 11 meeting minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-11-11/minutes.md)
- [MISRA C++ mapping PR #1226](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)
- [#1255 Questions left from the mapping review](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1255)
- [#1256 FFI scope in the standards mappings](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1256)
- [#1257 Function-local statics](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1257)
- [FLS Audit Guide](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/blob/main/docs/fls-audit.md)
