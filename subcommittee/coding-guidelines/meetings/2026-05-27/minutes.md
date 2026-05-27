# **Coding Guidelines Subcommittee Meeting on 2026-05-27 @ 1600 CEST / 1100 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848&h=5&date=2026-5-27&sln=11-12&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-05-13/minutes.md)
3. Introduction of new members
4. SCRC Room at Utrecht, NL
- Summary by Pete and others present. Notes: [Full Consortium Meeting: 21 May 2026, Utrecht, Netherlands](https://docs.google.com/document/d/1xpq2LD2wwMY6wmxMZRySkKiyXOReE4GGRaqFwqmJPDM/edit?tab=t.0#heading=h.ms5rnn5lex9g)
5. Coverage of MISRA C and CERT C in 2026 (Félix / Markus updates)
- MISRA C one has a [PR up](https://github.com/rustfoundation/safety-critical-rust-coding-guidelines/pull/432) from Markus
  - Preview was not working; got support from Joel Marcey to update settings on GitHub. Still needs to be tested with new pushed commit
  - Last week at RustWeek SCRC Room, Oreste expressed some interest in turning the CERT C mapping into an appendix
6. Interest in the MISRA C++ mapping
- Pete/Alex are working out how we can have some kind of copy of the MISRA documents (C, C++) held in the jurisdiction of the Rust Foundation in support of members to be able to work on coding guidelines
- Achim/Douglas/Max: Would you like to share the mapping done so far?
- Please register interest on [this Zulip thread](https://rust-lang.zulipchat.com/#narrow/channel/579369-safety-critical-consortium.2Fcoding-guidelines/topic/MISRA.20C.2B.2B.20Mapping.20Interest/with/584764785)
7. Overview of [Safety-Critical Rust](https://rust-lang.github.io/rust-project-goals/2026/roadmap-safety-critical-rust.html)  Rust Project Goals Roadmap (Pete)
- Soliciting those interested in [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html) goal
  - We had a meeting with two Rust Project Operational Semantics Team members yesterday.
  - Some initial useful feedback obtained; next steps are to develop small reproducible examples of the full iceoryx2 library portions there are questions on
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip
- Soliciting those interested in [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html) goal
  - Meeting with Jason Newcomb of Rust Project Clippy Team was immediately prior to this meeting
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip
8. Review batches for [CERT C  Rust Mapping](https://github.com/rustfoundation/safety-critical-rust-coding-guidelines/issues/336) (Pete)
   - Let's split up again, to get some feedback on batch 2
   - [428 \[CERT C Review Batch 2/5\] Review proposed Rust categorization](https://github.com/rustfoundation/safety-critical-rust-coding-guidelines/issues/428)
9. Round table

## **Check-in area**

* Pete LeVasseur
* Douglas Deslauriers 📜
* Michael Henn 🥵
* Max Jacinto 🍀
* Mira Baumann
* Christof Petig 🥵
* Achim Kriso 🦆
* William Barsse

**Notetaker:**

- Douglas Deslauriers

For tips on how we take notes in the Safety-Critical Rust Consortium, please see the [Meeting Notetaker Role](https://github.com/rustfoundation/safety-critical-rust-consortium/blob/main/docs/notetaker-role.md) doc.

## **Housekeeping section**

- Document space: [coding-guidelines](https://github.com/rustfoundation/safety-critical-rust-consortium/tree/main/subcommittee/coding-guidelines)
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)
  - [`contributor experience`](https://github.com/orgs/rustfoundation/projects/1/views/4) view
  - [`coding guideline`](https://github.com/orgs/rustfoundation/projects/1/views/5) view

## **Tasks**

- \[Pete\] Get back to Clippy team about the format of the reports
  - Stefan might be a good person to ask about this as someone who works with safety auditors
- \[Pete\] Give Doug access to the MISRA C++ Mapping sheet
- \[Pete\] Reach out to Andreas to see if he is interested in the MISRA C++ mapping
- \[Pete\] Ask Andreas for small examples with minimal context for the future meeting with Ralph
- \[Max\] Check if the Rust error numbers are “stable” or subject to change

## **Meeting Minutes**

- New Member Introduction
  - One new member (Mira) was introduced
- Rust Week SCRC Room
  - Pete gave a talk about Rust use at Toyota
  - Automotive suppliers and OEM integrators were also talking about Rust
  - There will be meeting notes available eventually, but for now in [google docs form](https://docs.google.com/document/d/1xpq2LD2wwMY6wmxMZRySkKiyXOReE4GGRaqFwqmJPDM/edit?tab=t.0#heading=h.ms5rnn5lex9g)
  - Break-out groups in the afternoon seemed to work well.
  - Stories about the usage of safety critical Rust are good, which can then be used as testimonials and promote usage broadly.
  - Funding was discussed and should be directed as generally as possible, to help support initiatives that overlap the most standards and platforms.
  - Pete interviewed some people to speak about safety critical topics.
  - There was a Clippy breakout session, where the SCRC was asked which lints were requested and how reports should be put together.
- Rust Guideline Mappings
  - The previews on the MISRA C appendix were broken, but should be fixed now
  - There was some interest in turning the CERT C mapping issues into an appendix
  - Pete will make some issues to help us track these mappings
  - Achim and Max has been working on the MISRA C++ mappings which is tracked in a [GitHub Issue \#575](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)
  - Max has been adding Rust examples to the mappings to help explain the rationale, and also mentions the error number when something doesn’t apply
  - For the MISRA C++ mapping feel free to claim some rules and update the [shared sheet](https://docs.google.com/spreadsheets/d/12e9Tr8PUTvVr87nUH0MQTwL31yU6YihQVxlvkqlo9SA/edit?gid=0#gid=0) after requesting access
  - Currently the MISRA C/C++ documents are not free, and required to work on these mappings
  - The SCRC is reaching out to MISRA to get organizational licenses for the documents
  - If more discussion is needed on a rule mapping, feel free to discuss in the [Zulip thread](https://rust-lang.zulipchat.com/#narrow/channel/579369-safety-critical-consortium.2Fcoding-guidelines/topic/MISRA.20C.2B.2B.20Mapping.20Interest/with/591892637). If a discussion gets complex enough, then a meeting may occur
- Rust Project Goals Roadmap
  - Was discussed as part of Rust Week where the Clippy team and t-opsec took part
  - There are some notes available, once published
  - The next step is going to be a meeting with the t-opsec team, in perhaps a few weeks, to generate some examples to demonstrate how the Rust abstract machine should work.
  - There was a meeting with the Clippy team, which will also eventually have notes, that explains the steps to help contribute lints
  - A few lints are in the process of being contributed by the SCRC
  - There was general approval for these meetings between the SCRC and t-opsec and Clippy
