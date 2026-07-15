# **Coding Guidelines Subcommittee Meeting on 2026-07-08 @ 1600 CEST / 1100 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-7-8&sln=11-12&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker  
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-07-01/minutes.md)  
3. Introduction of new members  
4. Solicit availability for RustConf 2026 SCRC Room (Pete)  
   - Please put availability on this [LettuceMeet](https://lettucemeet.com/l/oYlvM)  
5. The SCRC as a member organization of the Rust Commercial Network (RCN)  
   - [RFC PR](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium-rfcs/pull/8) has merged  
6. One-off feedback session on Clippy lint mapping to usefulness for safety-critical purposes (David / Pete)  
   - David and Félix will run this session; they are looking at around Thursday, July 16th (2026-07-16)  
   - Please note your interest in [this Zulip thread](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Clippy-linters/with/607612630)\\ and post availability on this [LettuceMeet](https://lettucemeet.com/l/gm2aK)  
7. Pete will be out of pocket for two weeks and would like to have someone sub in for hosting next week’s (July 15th) and the week after’s meeting (July 22nd)  
   - Pete will post a thread on Zulip about this soliciting who would like to run the meeting 🏃  
8. Safety-Critical Rust: Items of Shared Value for Fund Pooling (Pete)  
   - A first (0th?) draft document is available here: [Safety-Critical Rust \- Items of Shared Value for Fund Pooling](https://docs.google.com/document/d/1E39cNTjK-5azCeWWFWS1jORsz9nqzMs4CNa6Rm68jV4/edit?usp=sharing)  
   - Small workgroup to draft more and refine  
   - Pete to post thread on Zulip to solicit interest  
9. Interest in the MISRA C++ mapping (mira / Pete)  
   - Updates on new things in the MISRA C++ \=\> Rust mapping  
   - In talks with MISRA folks still; but in practice the procedure outlined seemed reasonable to them  
   - Please register interest on [this Zulip thread](https://rust-lang.zulipchat.com/#narrow/channel/579369-safety-critical-consortium.2Fcoding-guidelines/topic/MISRA.20C.2B.2B.20Mapping.20Interest/with/584764785)  
10. Walkthrough of Eclipse iceoryx2 stand-alone examples  
    - In pursuit of this Rust Project Goal: [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html)  
    - Available here: [https://github.com/ekxide/iox2-scrc-examples](https://github.com/ekxide/iox2-scrc-examples)  
    - Goal: familiarize ourselves enough to have follow-up session with t-opsem  
11. Round table

## **Check-in area**

- Mira Baumann  ☁️  
- Oreste Bernardi 🌧️  
- Samuel Wright ⛺  
- Daniel Dia 🌅  
- Pete LeVasseur 🌭  
- Marcos Borges 😀  
- William Barsse🌡️  
- Achim

**Notetaker:**

- Oreste Bernardi

For tips on how we take notes in the Safety-Critical Rust Consortium, please see the [Meeting Notetaker Role](https://github.com/rustfoundation/safety-critical-rust-consortium/blob/main/docs/notetaker-role.md) doc.

## **Housekeeping section**

- Document space: [coding-guidelines](https://github.com/rustfoundation/safety-critical-rust-consortium/tree/main/subcommittee/coding-guidelines)  
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)  
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)  
  - [`contributor experience`](https://github.com/orgs/rustfoundation/projects/1/views/4) view  
  - [`coding guideline`](https://github.com/orgs/rustfoundation/projects/1/views/5) view

## **Tasks**

- Pete shall setup a conf call with expert regarding the usage of `unsafe` in the zerocopy crate. In particular of interest is whether they have to rely on any syscalls.

## **Meeting Minutes**

- Previous meeting  
  - Approved  
- Solicit availability for RustConf 2026 SCRC Room  
  - No comments  
- One-off feedback session on Clippy lint mapping to usefulness for safety-critical purposes  
  - No comments  
- Substitute of Pete (next 2 week)  
  - Post in Zulip. No one is available.  
- Safety-Critical Rust: Items of Shared Value for Fund Pooling  
  - There will be a Zulip thread  
- Interest in the MISRA C++ mapping  
  - Some discussion is on going  
  - Many thanks to Mira.  
  - Things are moving faster than expected. Pretty good pace.  
- Walkthrough of Eclipse iceoryx2 stand-alone examples  
  - Quick review of [https://github.com/ekxide/iox2-scrc-examples/tree/main](https://github.com/ekxide/iox2-scrc-examples/tree/main)  
  - Review example ex1\_subscriber\_aliasing  
    1. It is an example for internal API  
  - Review example ex2\_subscriber\_spooky\_action  
    1. Discussed some potential risk to have just spot answers without “big picture” (e.g. abstract machine)    
  - Review example ex5\_uninitialized\_memory  
    1. Discussed how is modeled mmap from compiler point of view.  

## **Material**

Any material to read before the meeting should be included here.

Overview of [Safety-Critical Rust](https://rust-lang.github.io/rust-project-goals/2026/roadmap-safety-critical-rust.html)  Rust Project Goals Roadmap (Pete)

- Soliciting those interested in [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html) goal  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip  
- Soliciting those interested in [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html) goal  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip

