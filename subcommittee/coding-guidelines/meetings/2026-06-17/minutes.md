# **Coding Guidelines Subcommittee Meeting on 2026-06-17 @ 1600 CEST / 1100 EDT**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848&h=5&date=2026-6-3&sln=11-12&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker  
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-06-10/minutes.md)  
3. Introduction of new members  
4. Solicit availability for RustConf 2026 SCRC Room  
- Please put availability on this [LettuceMeet](https://lettucemeet.com/l/oYlvM)  
5. Discuss possible 2-3 coding guidelines to choose for Clippy lints  
- Picking "decidable" ones probably good  
- Let's look here: [https://coding-guidelines.arewesafetycriticalyet.org/coding-guidelines/expressions/index.html](https://coding-guidelines.arewesafetycriticalyet.org/coding-guidelines/expressions/index.html)  
6. First version of MISRA C \+ CERT C Appendices [live](https://coding-guidelines.arewesafetycriticalyet.org/appendices/standards-matrices/index.html)  
- Pete will now mine these appendices for creating issues for contributors  
7. Liaison White Paper Solicitation (Alex)  
8. Interest in the MISRA C++ mapping (mira / Pete)  
- Updates on new things in the MISRA C++ \=\> Rust mapping  
- In talks with MISRA folks still; but in practice the procedure outlined seemed reasonable to them  
- Please register interest on [this Zulip thread](https://rust-lang.zulipchat.com/#narrow/channel/579369-safety-critical-consortium.2Fcoding-guidelines/topic/MISRA.20C.2B.2B.20Mapping.20Interest/with/584764785)  
9. Round table

## **Check-in area**

- Pete LeVasseur ➕  
- Oreste Bernardi 🌞  
- Markus Hosch 🤯  
- Max Jacinto 📖  
- Samuel Wright ☀️  
- Mira Baumann  
- Alex Celeste ☕  
- Achim Kriso 🦆  

**Notetaker:**

- Alex Celeste

For tips on how we take notes in the Safety-Critical Rust Consortium, please see the [Meeting Notetaker Role](https://github.com/rustfoundation/safety-critical-rust-consortium/blob/main/docs/notetaker-role.md) doc.

## **Housekeeping section**

- Document space: [coding-guidelines](https://github.com/rustfoundation/safety-critical-rust-consortium/tree/main/subcommittee/coding-guidelines)  
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)  
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)  
  - [`contributor experience`](https://github.com/orgs/rustfoundation/projects/1/views/4) view  
  - [`coding guideline`](https://github.com/orgs/rustfoundation/projects/1/views/5) view

## **Tasks**

- Alex: create an Issue listing the rules we have identified as applicable and their starting partial coverage lints  
- Sam: investigate lint ii (pointer as underscore)  
- Pete: investigate lint iii (integer to pointer, general conversions)  
- Pete: open an Issue for lint i (int as int)  
- Alex: circulate the zeroth Whitepaper draft onto Zulip with ideas jotted down by Pete  
- Pete: add a usage statement for copyrighted material to the shared drive and also to the end of the minutes template

## **Meeting Minutes**

- Previous minutes accepted with formatting fixes  
- Still need to decide on a day for the SCRC room at RustConf  
  - Also need to arrange the online component  
- Having had two expert sessions now the group is ready to pick out 2-3 Clippy lints to work on  
  - Reviewing the expression rules list: most are decidable, especially if type-oriented rather than value-oriented  
    1. No \`as\` with integers is extremely similar to existing lints (no blanket lint but a widening lint exists) e.g. \`[clippy::cast\_lossless](https://rust-lang.github.io/rust-clippy/master/index.html?search=cast_loss#cast_lossless)\` \- inexact match but demonstrates checking of \`as\`  
    2. \`as\`-pointer casts is also similar to existing lints e.g. \`[clippy::ptr\_as\_ptr](https://rust-lang.github.io/rust-clippy/master/index.html?search=underscore#as_pointer_underscore)\`, \`[clippy::as\_pointer\_underscore](https://rust-lang.github.io/rust-clippy/master/index.html?search=underscore#as_pointer_underscore)\` \- inexact match  
    3. Integer to pointer has some support as \`[integer-to-ptr-transmutes](https://doc.rust-lang.org/rustc/lints/listing/warn-by-default.html?highlight=int%20to%20pointer#integer-to-ptr-transmutes)\`, still only partial coverage (transmute only)  
    4. Shifting out of range and division by zero are not decidable, partial support in \`[arithmetic-overflow](https://doc.rust-lang.org/rustc/lints/listing/deny-by-default.html?highlight=shift#arithmetic-overflow)\` \- probably intent to split the shift rule into constant and dynamic versions for decidability as the more constrained case is still useful; the existing lint is focused on constant shift rhs values only; the general case of the rule needs to be changed to **undecidable**  
       1. Related lint in \`[clippy::arithmetic\_side\_effects](https://rust-lang.github.io/rust-clippy/master/?search=overflo#arithmetic_side_effects)\` which bans the native infix operators that have a risk of overflow behaviours  
    5. Integer to pointer conversions has two rules in the decidable and undecidable flavours; the decidable rule is partially covered by the lints above  
  - Is there a reason we are particularly interested in the underscore for this rule?  
    1. Converting to a \`dyn\` type is checked whereas converting between pointer types is (implicit) unsafe and unchecked  
- The Appendices are live\! GH Issues still to be generated from these, which may be a lot  
- Liaison White Paper Solicitation (Alex)  
  - Proposal paper on items of shared value to pool funding  
    1. For example: having the Guidelines completed; having Clippy lints written to enforce as many of the Guidelines as possible; having people with the Community dedicating time to that work; getting safety qualification for Clippy or other tools (bindgen etc); getting the guidance/documentation available to pursue qualification independently  
    2. All of these items should be hardware, OS, vendor generic, and aiming to be useful to all or any of the existing safety standards (auto, aero, etc)  
    3. Enlist the various topics from Rust Week into a draft document and then circulate on Zulip  
  - Identify users of guidelines  
  - Challenges in enforcing guidelines  
  - Vendor opportunities (tooling)  
  - Perspective of an assessor that has assessed Rust code  
  - Success stories of application of Clippy lints in safety-critical context  
- On MISRA C++  
  - Pete is in contact with David and Andrew at MISRA w.r.t supply of MISRA materials; agreeable so long as usage/access is restricted in some fashion to members of the WG only (i.e. MISRA C and MISRA C++ will be made visible to individual members)  
  - Same statement of use needs to go on all the meeting notes  
  - Mira continues to make progress on working through the MISRA C++ rules  
    1. The preprocessor remains an unstarted topic  
    2. Questions for Doug on certain specific rules

## **Material**

Any material to read before the meeting should be included here.

Overview of [Safety-Critical Rust](https://rust-lang.github.io/rust-project-goals/2026/roadmap-safety-critical-rust.html)  Rust Project Goals Roadmap (Pete)

- Soliciting those interested in [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html) goal  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip  
- Soliciting those interested in [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html) goal  
  - Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip
