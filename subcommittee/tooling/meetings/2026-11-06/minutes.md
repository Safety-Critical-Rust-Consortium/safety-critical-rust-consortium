# Tooling Subcommittee Meeting on 5 November \`2026 @ 4pm GMT

| Search Key | Description |
| :---- | :---- |
| \[todo\] | Action Item |
| \[decision\] | Something decided on |
| \[important\] | Key information |

## Agenda

1. Solicitation of notetaker  
2. Present new members  
3. Merge previous meeting notes \- N/A  
4. Rust Project Bridge Task Force  
   1. [https\://github.com/rust-lang/goals/issues/631](https://github.com/rust-lang/goals/issues/631)  
   2. [https\://github.com/rust-lang/goals/issues/644](https://github.com/rust-lang/goals/issues/644)   
   3. [https\://github.com/rust-lang/goals/issues/651](https://github.com/rust-lang/goals/issues/651)    
5. Rust Project Goal: Lossless Macro Expansion  
   1. [https\://github.com/pellico/rust\_goals/blob/feature/lossless-macro-expansion/src/2026/lossless-macro-expansion.md](https://github.com/pellico/rust_goals/blob/feature/lossless-macro-expansion/src/2026/lossless-macro-expansion.md)  
   2. [https\://github.com/rust-lang/compiler-team/issues/692](https://github.com/rust-lang/compiler-team/issues/692)  
   3. [https\://rust-lang.zulipchat.com/\#narrow/stream/233931-xxx/topic/Add.20hygiene.20attributes.20to.20compile.20expande.E2.80.A6.20compiler-team.23692](https://rust-lang.zulipchat.com/#narrow/stream/233931-xxx/topic/Add.20hygiene.20attributes.20to.20compile.20expande.E2.80.A6.20compiler-team.23692)  
6. Tool Submission PR: [https\://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/773](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/773)  
7. Standards List [https\://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/774](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/774)  
8. Embedded World Rust Foundation booth, any progress?  
9. Position paper PR ([https\://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/775](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/775))  
10. Verus tooling [https\://github.com/verus-lang/verus](https://github.com/verus-lang/verus)  
    1. Press release: [https\://www\.adacore.com/press/adacore-and-cmu-researchers-announce-collaboration-around-formal-verification-of-rust-for-high-integrity-systems](https://www.adacore.com/press/adacore-and-cmu-researchers-announce-collaboration-around-formal-verification-of-rust-for-high-integrity-systems)  
11. Proposal to gather feedback to improve well-used Rust tooling e.g Cargo

## Check-in area

**Please add your name, and an emoji that describes your day.**

* Mark Hermeling \- 🦆  
* Zalán Bálint Lévai 😴  
* Alexandru Radovici 🙂    
* Manuel Hatzl  
* Oreste Bernardi  
* Pete LeVasseur 🖖  
* .

 **Notetaker:**

* Oreste Bernardi

## Housekeeping section

* 

## Tasks

AI: Modify the position paper PR \[Alexandru\]

## Meeting Minutes

* Review Rust project goals 631,644,651  
  * Present effort concentrate on keeping up to data FLS  
* Review of Lossless Macro Expansion proposal  
  * It has been proposed that Zala’n  take over the proposal for Rust Project Goals  
  * There were already some discussions on this topic. See links in the previous section.  
  * The first technical proposal had many issues. There were other change proposals. Progress is understandably slow.  
  * Proposal that Zala’n is taking ownership to complete the Rust Project Goal proposal but not yet create the pull request.   
  * Pull request will be created after review and consulting interested stakeholder.  
  * Discussed the minimal requirements: some tool that expand code, generated code is compilable with qualified compiler, human readable.  
* Review tool submission PR (see link in Agenda section)  
  * Approved merge  
* Standard List (see link in Agenda section)  
  * Call for review  
* Embedded World  
  * Too late for 2027 embedded world.  
* Position PR  
  * Paper about the \`unsafe\` keyword doesn't mean unsafe  and how to deal with assessors.   
* Verus tooling  
  * Formal methods for Rust. Move some Rust checks from runtime to static verification.  
* Proposal to gather feedback to improve well-used Rust tooling  
  * Proposed to collect feedback from safety and security experts and bring to tool developers e.g. Cargo.  
  * Probably the Rust project and community are not very much interested in this topic.  
  * 