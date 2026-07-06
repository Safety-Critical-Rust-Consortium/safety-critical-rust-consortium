# **Coding Guidelines Subcommittee Meeting on 2026-07-01 @ 1600 CEST / 1100 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-7-1&sln=11-12&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker  
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-06-24/minutes.md)  
3. Introduction of new members  
4. Solicit availability for RustConf 2026 SCRC Room (Pete)  
    - Please put availability on this [LettuceMeet](https://lettucemeet.com/l/oYlvM)  
5. The SCRC as a member organization of the Rust Commercial Network (RCN)  
    - [RFC PR](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium-rfcs/pull/8)  
    - RCN announcement goes out today with the SCRC as a founding member organization  
6. Draft document for usage of standards documents  
    - Current draft: [Usage Terms of Standards Documents](https://docs.google.com/document/d/1ctOOMA81slp8N4Sja_FmeDLaneEmtyIplL9EtYilM3s/edit?usp=sharing)  
    - Located in the publicly accessible folder on the SCRC Google Drive: [Standards Documents](https://drive.google.com/drive/folders/1fgcca7tbpc0iLoZf1AQR_v9Kh51rungp?usp=drive_link)  
    - How do we feel about these? Suggestions?  
7. Discuss possible 2-3 coding guidelines to choose for Clippy lints (Pete)  
    - How've we done in looking into these?	  
8. One-off feedback session on Clippy lint mapping to usefulness for safety-critical purposes (David / Pete)
    - David and Félix will run this session; they are looking at around Thursday, July 16th (2026-07-16)
    - Please note your interest in [this Zulip thread](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Clippy-linters/with/607612630)!
9. First version of MISRA C \+ CERT C Appendices [live](https://coding-guidelines.arewesafetycriticalyet.org/appendices/standards-matrices/index.html)  
    - [CERT C](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/milestone/3) and [MISRA C](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/milestone/4) milestones now established
    - New labels (and board views): [`rationale needed`](https://github.com/orgs/Safety-Critical-Rust-Consortium/projects/4/views/12), [`guideline needed`](https://github.com/orgs/Safety-Critical-Rust-Consortium/projects/4/views/11), [`clippy lint needed`](https://github.com/orgs/Safety-Critical-Rust-Consortium/projects/4/views/13)
10. Safety-Critical Rust: Items of Shared Value for Fund Pooling (Pete)  
    - One of the action items Pete took from the SCRC Room at RustWeek 2026  
    - Things seem to be heating up with the formation of the Rust Foundation Maintainers Fund (RFMF) and Ecosystem Fund and the Funding Team. Would be good to make sure we make our needs and requests obvious and clear.  
    - Pete will screen share and show the draft and then share it afterwards for feedback  
    - Would we like to form up a working group temporarily to get this in good shape?  
    - A first (0th?) draft document is available here: [Safety-Critical Rust - Items of Shared Value for Fund Pooling](https://docs.google.com/document/d/1E39cNTjK-5azCeWWFWS1jORsz9nqzMs4CNa6Rm68jV4/edit?usp=sharing)  
11. Interest in the MISRA C++ mapping (mira / Pete)  
    - Updates on new things in the MISRA C++ \=\> Rust mapping  
    - In talks with MISRA folks still; but in practice the procedure outlined seemed reasonable to them  
    - Please register interest on [this Zulip thread](https://rust-lang.zulipchat.com/#narrow/channel/579369-safety-critical-consortium.2Fcoding-guidelines/topic/MISRA.20C.2B.2B.20Mapping.20Interest/with/584764785)  
12. Review batches for [CERT C  Rust Mapping](https://github.com/rustfoundation/safety-critical-rust-coding-guidelines/issues/336) (Pete)  
- Let's split up again, to get some feedback on batch 2  
- [428 \[CERT C Review Batch 2/5\] Review proposed Rust categorization](https://github.com/rustfoundation/safety-critical-rust-coding-guidelines/issues/428)  
- **Group A**  
  - xx  
- **Group B**  
  - Xx  
13. Round table

## **Check-in area**

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

- xx

## **Material**

Any material to read before the meeting should be included here.

Overview of [Safety-Critical Rust](https://rust-lang.github.io/rust-project-goals/2026/roadmap-safety-critical-rust.html)  Rust Project Goals Roadmap (Pete)

- Soliciting those interested in [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html) goal  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip  
- Soliciting those interested in [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html) goal  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip  

