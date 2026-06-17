# **Coding Guidelines Subcommittee Meeting on 2026-06-10 @ 1600 CEST / 1100 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848&h=5&date=2026-6-3&sln=11-12&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker  
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-06-03/minutes.md)  
3. Introduction of new members  
4. The SEI CERT Coding Standard for Fortran (David)  
- Read more here: [https://www.sei.cmu.edu/blog/the-sei-cert-coding-standard-for-fortran/](https://www.sei.cmu.edu/blog/the-sei-cert-coding-standard-for-fortran/)  
5. Coverage of MISRA C and CERT C in 2026 (Félix / Markus updates)  
- MISRA C one from Markus has [merged](https://github.com/rustfoundation/safety-critical-rust-coding-guidelines/pull/432)  
- CERT C one from Oreste has [also merged](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/582)  
  - Live now at: [https://coding-guidelines.arewesafetycriticalyet.org/appendices/standards-matrices/index.html](https://coding-guidelines.arewesafetycriticalyet.org/appendices/standards-matrices/index.html)  
  - Félix opened an [issue](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/585) to track usability improvements in the appendices that's up for grabs  
  - Pete will now mine these appendices for creating issues for contributors  
6. Interest in the MISRA C++ mapping (mira / Pete)  
- Updates on new things in the MISRA C++ \=\> Rust mapping  
- In talks with MISRA folks still; but in practice the procedure outlined seemed reasonable to them  
- Please register interest on [this Zulip thread](https://rust-lang.zulipchat.com/#narrow/channel/579369-safety-critical-consortium.2Fcoding-guidelines/topic/MISRA.20C.2B.2B.20Mapping.20Interest/with/584764785)  
7. Round table

## **Check-in area**

- David Svoboda (-:  
- Max Jacinto 📚  
- Kaneko Satoshi 🫥  
- Mira Baumann  
- Pete LeVasseur 💯  
- Oreste Bernardi 🧠  
- Markus Hosch

**Notetaker:**

- David Svoboda

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

- Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-06-03/minutes.md): Accepted  
- Introduction of new members  
- The SEI CERT Coding Standard for Fortran (David)  
- Read more here: [https://www.sei.cmu.edu/blog/the-sei-cert-coding-standard-for-fortran/](https://www.sei.cmu.edu/blog/the-sei-cert-coding-standard-for-fortran/)  
- Standards published for almost 20 years 🎉  
- Fortran is new and still has some areas of improvement  
  1. Rules: What to follow that are specific and should be followed  
  2. Recommendations: Things you can violate if you’re careful  
- [TYP02-F. Prohibit implicit typing in all program units](https://cmu-sei.github.io/secure-coding-standards/sei-cert-fortran-coding-standard/types-typ/typ02-f)  
  1. Kind of odd; don’t have to declare before usage  
  2. If you just start using a variable, the letter that this variable name begins with determines its type  
  3. Recommended to, for all variables explicitly declare types of them  
- CERT C has on the order of \~200+ total rules and recommendations, so call to action for if anyone else would like   
6. Coverage of MISRA C and CERT C in 2026 (Félix / Markus updates)  
- MISRA C one from Markus has [merged](https://github.com/rustfoundation/safety-critical-rust-coding-guidelines/pull/432)  
- CERT C one from Oreste has [also merged](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/582)  
  - Live now at: [https://coding-guidelines.arewesafetycriticalyet.org/appendices/standards-matrices/index.html](https://coding-guidelines.arewesafetycriticalyet.org/appendices/standards-matrices/index.html)  
  - Félix opened an [issue](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/585) to track usability improvements in the appendices that's up for grabs  
  - Pete will now mine these appendices for creating issues for contributors  
  - Oreste: Items marked as ‘maybe’ are applicable to Rust. Formatting is a bit strange.   
  - Pete: Will you create a new issue with whatever you consider needs still to be done?  
  - Oreste: OK  
7. Interest in the MISRA C++ mapping (mira / Pete)  
- Updates on new things in the MISRA C++ \=\> Rust mapping  
- In talks with MISRA folks still; but in practice the procedure outlined seemed reasonable to them  
- Please register interest on [this Zulip thread](https://rust-lang.zulipchat.com/#narrow/channel/579369-safety-critical-consortium.2Fcoding-guidelines/topic/MISRA.20C.2B.2B.20Mapping.20Interest/with/584764785)  
- Mira: Most missing stuff is about inheritance. Would like review. Also lots of items about the standard library.   
- David: Difficult because MISRA C++ is not free.  
- Mira: Yes. I had to buy it.  
- Markus: Applicability of inheritance to Rust. Traits do have inheritance.  
- Mira: MISRA C++ was mostly about virtual inheritance. Also it has very little rules about templates.  
- Markus: It is good to think about how rules would apply in alternate technologies.   
- Pete: I have enlisted a MISRA C++ member to help out.  
8. Review batches for [CERT C  Rust Mapping](https://github.com/rustfoundation/safety-critical-rust-coding-guidelines/issues/336) (Pete) (tabled)  
9. Round table  
- 

## **Material**

Any material to read before the meeting should be included here.

Overview of [Safety-Critical Rust](https://rust-lang.github.io/rust-project-goals/2026/roadmap-safety-critical-rust.html)  Rust Project Goals Roadmap (Pete)

- Soliciting those interested in [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html) goal  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip  
- Soliciting those interested in [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html) goal  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip

