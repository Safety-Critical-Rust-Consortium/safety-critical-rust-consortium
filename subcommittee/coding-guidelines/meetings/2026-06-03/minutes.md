# **Coding Guidelines Subcommittee Meeting on 2026-06-03 @ 1600 CEST / 1100 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848&h=5&date=2026-6-3&sln=11-12&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker  
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-05-27/minutes.md) and [Previous Asia Pacific \+ Americas Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-05-29/minutes.md)  
3. Introduction of new members  
4. Coverage of MISRA C and CERT C in 2026 (Félix / Markus updates)  
- MISRA C one has a [PR up](https://github.com/rustfoundation/safety-critical-rust-coding-guidelines/pull/432) from Markus  
  - Félix is working on CSS to make the tables more legible by allowing them to be shown more widely.  
  - Oreste: Pick up CERT C Markdown tables in tracking issue and open up a PR similar in nature to the [PR from Markus](https://github.com/rustfoundation/safety-critical-rust-coding-guidelines/pull/432)  
    1. Issue, where it’s written up in Markdown: [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/336](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/336)  
    2. Turn into a PR with the tables in ReStructured Text (RST)  
5. Interest in the MISRA C++ mapping  
- Pete/Alex are working out how we can have some kind of copy of the MISRA documents (C, C++) held in the jurisdiction of the Rust Foundation in support of members to be able to work on coding guidelines. Still in communication with MISRA folks.  
- Please register interest on [this Zulip thread](https://rust-lang.zulipchat.com/#narrow/channel/579369-safety-critical-consortium.2Fcoding-guidelines/topic/MISRA.20C.2B.2B.20Mapping.20Interest/with/584764785)  
6. Review batches for [CERT C  Rust Mapping](https://github.com/rustfoundation/safety-critical-rust-coding-guidelines/issues/336) (Pete)  
- Let's split up again, to get some feedback on batch 2  
- [428 \[CERT C Review Batch 2/5\] Review proposed Rust categorization](https://github.com/rustfoundation/safety-critical-rust-coding-guidelines/issues/428)  
- **Group A**  
  - Wednesday, June 3 · 11:30am – 12:00pm  
  - Time zone: America/New\_York  
  - Google Meet joining info  
    1. Achim  
    2. Daniel Dia  
    3. Kaneko Satoshi  
    4. Marcos Borges  
  - Xxxxxx  
- **Group B**  
  - Wednesday, June 3 · 11:30am – 12:00pm  
  - Time zone: America/New\_York  
  - Google Meet joining info  
    1. Max  
    2. Michael  
    3. Mira  
    4. Pete  
    5. Oreste  
  -   
7. Round table

## **Check-in area**

* Marcos Borges 😀  
* Max Jacinto 🏋️  
* Daniel Dia 🦀  
* Oreste Bernardi   
* Mira Baumann   
* Pete LeVasseur ⚰️➕➕  
* Michael Henn 🏃

**Notetaker:**

- Max Jacinto

For tips on how we take notes in the Safety-Critical Rust Consortium, please see the [Meeting Notetaker Role](https://github.com/rustfoundation/safety-critical-rust-consortium/blob/main/docs/notetaker-role.md) doc.

## **Housekeeping section**

- Document space: [coding-guidelines](https://github.com/rustfoundation/safety-critical-rust-consortium/tree/main/subcommittee/coding-guidelines)  
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)  
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)  
  - [`contributor experience`](https://github.com/orgs/rustfoundation/projects/1/views/4) view  
  - [`coding guideline`](https://github.com/orgs/rustfoundation/projects/1/views/5) view

## **Tasks**

- xx

## **Meeting Minutes**

- Confirmation if everything’s alright with previous meetings’ minutes; all good, none against  
- Introduction of new members\! Two new members join us  
- **\[MISRA C\]**  
  - Work on the appendix’s formatting is being done; mainly fixes in how the tables are shown  
- **\[CERT C\]**  
  - Pending task to format the tables accordingly (Markdown conversion \- formatted text); should be sent as a PR to be merged  
  - Suggestion to use `pandoc` to convert Markdown to other formats (like RST)  
- **\[MISRA C++\]**  
  - Interest in checking out rules specific to C++ that may involve concepts like polymorphism  
  - Communication through the Zulip thread is highly encouraged\! If there’s any need for a review or help with a rule volunteers are more than encouraged to leave a message  
- **\[Walk-In Items\]**  
  - Consortium mailing list has been sent a Lettucemeet to check availability for RustConf of SCRC members that will attend  
  - ADACore has agreed to fund a room at RustConf; ongoing talks to figure out the best structure for the deal  
  - *Suggestion regarding GH organization:* creation of topics that combine common subjects to better keep track of conversations; aim is to reduce fragmentation  
- **\[CERT C Review Batches\]**  
  - **Group 1:**  
    - ARR38: Full agreement  
    - STR32: Agreement for safe Rust, but when doing interop with C libraries you will likely work with raw pointers that point to zero terminated and non-zero terminated buffers, which could be confused. Therefore, it should be considered to update the classification from “Does not map to Rust” to “Maps directory to Unsafe Rust”. Furthermore, the \`CString\` and \`CStr\` types should be acknowledged by the Rationale explicitly for completeness.  
  - **Group 2:**  
    - **ERR33:**   
      - Suggest that there’s a Clippy lint (`clippy::unused_results`) that can force `Return` return values ([https://play.rust-lang.org/?version=stable\&mode=debug\&edition=2024](https://play.rust-lang.org/?version=stable&mode=debug&edition=2024))  
      - Extra context: [https://play.rust-lang.org/?version=stable\&mode=debug\&edition=2024\&gist=ec6c707cad086431258894b336654df8](https://play.rust-lang.org/?version=stable&mode=debug&edition=2024&gist=ec6c707cad086431258894b336654df8)  
    - **INT33:** Suggestion to add a reference link to the specific rule that covers it if that’s the case  
- **\[ROUNDTABLE\]**  
  - Clarification regarding the established rules found in, for example: [https://coding-guidelines.arewesafetycriticalyet.org/coding-guidelines/expressions/index.html](https://coding-guidelines.arewesafetycriticalyet.org/coding-guidelines/expressions/index.html)  
    - Request for PR regarding the clarification issues

## **Material**

Any material to read before the meeting should be included here.

Overview of [Safety-Critical Rust](https://rust-lang.github.io/rust-project-goals/2026/roadmap-safety-critical-rust.html)  Rust Project Goals Roadmap (Pete)

- Soliciting those interested in [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html) goal  
  - We had a meeting with two Rust Project Operational Semantics Team members yesterday.  
  - Some initial useful feedback obtained; next steps are to develop small reproducible examples of the full iceoryx2 library portions there are questions on  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip  
- Soliciting those interested in [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html) goal  
  - Meeting with Jason Newcomb of Rust Project Clippy Team was immediately prior to this meeting  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip

