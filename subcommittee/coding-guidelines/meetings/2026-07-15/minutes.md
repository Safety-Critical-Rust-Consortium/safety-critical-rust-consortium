# **Coding Guidelines Subcommittee Meeting on 2026-07-15 @ 1600 CEST / 1100 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-7-15&sln=11-12&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker  
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-07-08/minutes.md)  
3. Introduction of new members  
4. Interest in the MISRA C++ mapping (mira / Pete)  
   - Updates on new things in the MISRA C++ \=\> Rust mapping  
   - In talks with MISRA folks still; but in practice the procedure outlined seemed reasonable to them  
   - Please register interest on [this Zulip thread](https://rust-lang.zulipchat.com/#narrow/channel/579369-safety-critical-consortium.2Fcoding-guidelines/topic/MISRA.20C.2B.2B.20Mapping.20Interest/with/584764785)  
5. Working session: review feedback on the [CERT C to Rust coding guidelines mapping](https://coding-guidelines.arewesafetycriticalyet.org/appendices/standards-matrices/cert-c-2016-mapping.html)  
   - Parent tracking issue: [\#336 Mapping of CERT C to Rust Guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/336)  
   - Review batches: [1/5](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/427), [2/5](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/428), [3/5](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/429), [4/5](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/430), and [5/5](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/431)  
     - The [2/5 batch](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/428) has the most as-yet unreviewed mappings, but some others have them here or there too.  
   - Goal: work through review feedback, confirm or revise the proposed Rust categorization, and capture decisions and follow-up work in the relevant issues  
   - **Group A \- first 7 rules from 2/5**  
     - [https://meet.google.com/muk-bsjv-oke](https://meet.google.com/muk-bsjv-oke)  
     - Group:  
       1.   
   - **Group B \- 4 last rules from 2/5 and 4/5**  
     - [https://meet.google.com/svx-rtsv-izb](https://meet.google.com/svx-rtsv-izb)  
     - Group:  
       1.   
6. Round table

## **Check-in area**

- Mira Baumann 🌞  
- Daniel Dia 💾  
- Christof Petig 🤖
- Samuel Wright 🐻  
- Alex Celeste ☕  
- William Barsse 🌡️  
- Achim Kriso 🦆  
- Markus Hosch🤯

**Notetaker:**

- Christof Petig

For tips on how we take notes in the Safety-Critical Rust Consortium, please see the [Meeting Notetaker Role](https://github.com/rustfoundation/safety-critical-rust-consortium/blob/main/docs/notetaker-role.md) doc.

## **Housekeeping section**

- Document space: [coding-guidelines](https://github.com/rustfoundation/safety-critical-rust-consortium/tree/main/subcommittee/coding-guidelines)  
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)  
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)  
  - [`contributor experience`](https://github.com/orgs/rustfoundation/projects/1/views/4) view  
  - [`coding guideline`](https://github.com/orgs/rustfoundation/projects/1/views/5) view

## **Tasks**

- n.a.

## **Meeting Minutes**

- Meeting minutes were accepted with no objections  
- No new members on the call  
- Mira reported that there are four items left for grab on MISRA C++ mappings  
- One group will go for the first seven rules of 2/5, the other group for the last four of 2/5 and all three in ⅘  
  - The second group was unable to join the sub-meeting without invitation from the organizer, so the group returned to the main meeting for the discussion  
- Subgroups returned to the main meeting.  
  - Group 2 will create an issue with their comments which then can be linked from the review issue.  
    - [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/131](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/131)  
    - [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/132/changes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/132/changes)  
    -   
  - Group 1: FIO39 is more unclear on how it is actually implemented in Rust  
    - [https://doc.rust-lang.org/std/io/index.html\#io-safety](https://doc.rust-lang.org/std/io/index.html#io-safety) \- it feels like this might need some rule about file I/O  
    - New issue [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/428\#issuecomment-4982470186](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/428#issuecomment-4982470186)   
- Roundtable:  
  - Do we want to recommend the format for justification for required rules?  
    - MISRA 2020 has guidance on these  
    - Standardizing on the existence of a reason field for required rules feels like consensus, but the contents of the field are left to the implementer

## **Material**

Any material to read before the meeting should be included here.

Overview of [Safety-Critical Rust](https://rust-lang.github.io/rust-project-goals/2026/roadmap-safety-critical-rust.html) Rust Project Goals Roadmap (Pete)

- Soliciting those interested in [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html) goal  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip  
- Soliciting those interested in [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html) goal  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip
