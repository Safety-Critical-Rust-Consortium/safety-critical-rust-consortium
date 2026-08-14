# Tooling Subcommittee Meeting on 14 August 2026 @ 4pm GMT

| Search Key | Description |
| :---- | :---- |
| \[todo\] | Action Item |
| \[decision\] | Something decided on |
| \[important\] | Key information |

## Agenda

1. Solicitation of notetaker  
2. Present new members  
3. Merge previous meeting notes (Pete was not aware of the previous PR, oops)  
4. SCRC Room @ RustConf 2026  
   1. Please list availability in this LettuceMeet 🥬[https://lettucemeet.com/l/oYlvM](https://lettucemeet.com/l/oYlvM)   
5. Tooling  
   1. Tooling folder cleanup:   
      1. [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/683](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/683)  
      2. Merge this one?  
   2. Tooling acceptance criteria:  
      1. [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/700](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/700)  
6. Rust Project Bridge  
   1. [Stabilize FLS Release Cadence](https://rust-lang.github.io/goals/2026/stabilize-fls-releases.html)  
      1. FLS Team working to get 1.97 release of FLS out before 1.98 release next Thursday  
      2. [One PR](https://github.com/rust-lang/fls/pull/717) that maybe should go in, fixing up imports, before we review and then merge [1.97 content](https://github.com/rust-lang/fls/pull/713) and then release  
   2. [Normative Documentation for Sound `unsafe` Rust](https://rust-lang.github.io/goals/2026/safe-unsafe-for-safety-critical.html)  
      1. Eclipse iceoryx2 maintainers have updated [https://github.com/ekxide/iox2-scrc-examples](https://github.com/ekxide/iox2-scrc-examples) with [stories](https://github.com/ekxide/iox2-scrc-examples/blob/main/Stories.md) that can be told about their usage of unsafe, in-line with a suggestion by RalfJ  
      2. Andreas Weiss will ask in the t-opsem Zulip stream about the bit they have about Safety, which is mostly either (1) non-controversial or (2) calling into platform primitives  
      3. We will aim for a follow-up meeting with RalfJ  
   3. [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/goals/2026/safety-critical-lints-in-clippy.html)  
      1. Coding Guidelines Subcommittee has not made further progress to attempt to document / write up these lints  
   4. [Implement and Maintain MC/DC Coverage Support](https://rust-lang.github.io/goals/2026/mcdc-coverage-support.html)  
      1. [July update](https://github.com/rust-lang/goals/issues/638#issuecomment-4956366945) was posted for the Rust Project Goal

## Check-in area

**Please add your name, and an emoji that describes your day.**

* Mark Hermeling ⛵  
* Tiago Manczak ☀️  
* Jeongsoo Lee 😊  
* Pete LeVasseur 🇨🇦  
* Oreste Bernardi 🫠⛰️

 **Notetaker:**

* Tiago Manczak

## Housekeeping section

## Tasks

* \[todo\] Mark Hermeling \- Create issue to improve tools acceptance criteria  
* \[todo\] Oreste \- create an issue about the story telling mentioning the difference about directives vs rules for the embedded use case

## Meeting Minutes

* Jeongsoo Lee (CodeQL) \- joined the Tooling group and  presented himself  
* Attendance of RustConf addressed  
* Merged [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/683](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/683)  
* Discussed [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/700](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/700)  
  * \[decision\] Merge the PR with acceptance of the meeting participants  
* Rust Bridge  
  * FLS  
    * targeting Rust version 1.98  
  * Unsafe Rust  
    * Blog post: [https://www.ralfj.de/blog/2026/03/13/inline-asm.html](https://www.ralfj.de/blog/2026/03/13/inline-asm.html)  
    * Discussion will take place with Operational Semantics Team (t-opesem) about Platform primitives  
    * Same storytelling approach might be able to be used with low-level hardware drivers  
  * Clippy  
    * Support to write clippy lints is welcome  
      * Volunteer can get involved over the Zulip channel: [https://rust-lang.zulipchat.com/\#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/near/606989191](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/near/606989191)  
  * MC/DC Coverage  
    * Reported progress  
      * New updates on schedules  
      * Implementation currently done on internal fork at AdaCore  
      * Suggestion is to make it public and create a roadmap for multiple PRs  
      * Current state is not stable though and team is working on the necessary fixes