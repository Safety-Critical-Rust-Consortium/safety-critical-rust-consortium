# **Coding Guidelines Subcommittee Meeting on 2026-05-29 @ 1600 CEST / 1100 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848&h=5&date=2026-5-28&sln=19-20&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker  
2. Introduction of new members  
3. SCRC Room at Utrecht, NL  
- Summary by Pete and others present  
5. Coverage of MISRA C and CERT C in 2026 (Félix / Markus updates)  
- MISRA C one has a [PR up](https://github.com/rustfoundation/safety-critical-rust-coding-guidelines/pull/432) from Markus  
  - Preview was not working; got support from Joel Marcey to update settings on GitHub. Still needs to be tested with new pushed commit  
- Last week at RustWeek SCRC Room, Oreste expressed some interest in turning the CERT C mapping into an appendix  
6. Interest in the MISRA C++ mapping  
- Pete/Alex are working out how we can have some kind of copy of the MISRA documents (C, C++) held in the jurisdiction of the Rust Foundation in support of members to be able to work on coding guidelines  
- Tracking issue is [here](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)  
- Please register interest on [this Zulip thread](https://rust-lang.zulipchat.com/#narrow/channel/579369-safety-critical-consortium.2Fcoding-guidelines/topic/MISRA.20C.2B.2B.20Mapping.20Interest/with/584764785)  
7. Overview of [Safety-Critical Rust](https://rust-lang.github.io/rust-project-goals/2026/roadmap-safety-critical-rust.html)  Rust Project Goals Roadmap (Pete)  
- Soliciting those interested in [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html) goal  
  - We had a meeting with two Rust Project Operational Semantics Team members two days ago.  
  - Some initial useful feedback obtained; next steps are to develop small reproducible examples of the full iceoryx2 library portions there are questions on  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip  
- Soliciting those interested in [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html) goal  
  - Meeting with Jason Newcomb of Rust Project Clippy Team was done yesterday  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip  
8. Review batches for [CERT C  Rust Mapping](https://github.com/rustfoundation/safety-critical-rust-coding-guidelines/issues/336) (Pete)  
- Let's split up again, to get some feedback on batch 2  
- [428 \[CERT C Review Batch 2/5\] Review proposed Rust categorization](https://github.com/rustfoundation/safety-critical-rust-coding-guidelines/issues/428)  
9. Round table

## **Check-in area**

* Yuchen Shen ☕  
* Félix Fischer ⚡  
* Mikhail Antoshkin ☕  
* Max Jacinto 📚  
* Pete LeVasseur 🌃

**Notetaker:**

- Yuchen

For tips on how we take notes in the Safety-Critical Rust Consortium, please see the [Meeting Notetaker Role](https://github.com/rustfoundation/safety-critical-rust-consortium/blob/main/docs/notetaker-role.md) doc.

## **Housekeeping section**

- Document space: [coding-guidelines](https://github.com/rustfoundation/safety-critical-rust-consortium/tree/main/subcommittee/coding-guidelines)  
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)  
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)  
  - [`contributor experience`](https://github.com/orgs/rustfoundation/projects/1/views/4) view  
  - [`coding guideline`](https://github.com/orgs/rustfoundation/projects/1/views/5) view

## **Tasks**

- Pete will share a link about using CSS to format RST file  
- Félix will share his local work for CERT C rules with Max.

## **Meeting Minutes**

- Standard Matrices \- Rust Cross Reference with MISRA C 2025  
  - Need help to format the RST using CSS;   
  - Recommendation to have more discussion and work on the Table \- 1\. Some of the rules are considered not applicable.  
- MISRA C++ to Rust mapping initiative: [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575). Welcome contribution if anyone has interests  
  - Things wanted:   
    - Add examples in rationale to show what works and what not  
    - Add recommendation on what clippy lint rules can be used  
  - Miri is questionable to recommend and needs more discussion. Only Clippy mentioned currently, not Miri: [https://arewesafetycriticalyet.org/tooling/tools-list](https://arewesafetycriticalyet.org/tooling/tools-list)  
- Some extra materials to read for fun and inspiration  
  - [https://github.com/soteria-tools/soteria](https://github.com/soteria-tools/soteria)  
- Notes from[t-opsem - meeting - 2026-05-26](https://docs.google.com/document/d/1RpvlY_b9Z3DyKOpHfJ8VF6VRDUMhlfdHu8ztIciJ6EI/edit?tab=t.0#heading=h.ms5rnn5lex9g) and [t-clippy - meeting - 2026-05-27](https://docs.google.com/document/d/1YFIytC7TuBZY2D3TG8zYgDc-4k85O_GrvHBNV19hwmE/edit?tab=t.0#heading=h.ms5rnn5lex9g)  
- [https://deploy-preview-432--scrc-coding-guidelines.netlify.app/coding-guidelines/types-and-traits/gui\_0cutyg8rvyjg\#non\_compl\_ex\_ecHYRXb4Ncpu](https://deploy-preview-432--scrc-coding-guidelines.netlify.app/coding-guidelines/types-and-traits/gui_0cutyg8rvyjg#non_compl_ex_ecHYRXb4Ncpu) Examples of code being able to be compiled with Miri; would be great to have this for FFI code that applies to rules in CERT C/MISRA C/MISRA C++  
- [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/370](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/370) Request for review\!

## **Material**

Any material to read before the meeting should be included here.  
