# Tooling Subcommittee Meeting on 19 June 2026 @ 4pm GMT

| Search Key | Description |
| :---- | :---- |
| \[todo\] | Action Item |
| \[decision\] | Something decided on |
| \[important\] | Key information |

## Agenda

1. Solicitation of notetaker
2. Present new members
   1. Mark Hermeling (AdaCore) (2nd time new :)
3. Merge previous meeting notes (?)
   1. [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/686](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/686)
4. SCRC Room @ RustConf 2026
   1. Please list availability in this LettuceMeet 🥬[https://lettucemeet.com/l/oYlvM](https://lettucemeet.com/l/oYlvM)
5. Tooling
   1. Repo cleanup [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/683](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/683)
   2. DO-330 mention [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/684](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/684)
   3. New railway standard EN 50716 [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/685](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/pull/685)
   4. List of safety-critical standards to purchase
      \*\*Standards:\*\*
      \- ISO 26262 … automotive
      \- DO-178C … main aerospace standard
      \- DO-330 … tool qualification
      \- DO-331 … formal methods
      \- DO-332 … memory management
      \- DO-333 … model-based development
      \- IEC 62304 … medical
      \- IEC 61508 … industrial
      \- EN 50716 … railway (Note: supersedes EN 50128\)
      \- IEC 60880 … nuclear power plants
      \- IEC 61226 … safety category classification
      \- IEC 62138 … software aspects for lower-level categories B and C
      \- IEC 61513 … general requirements for instrumentation and control
      \- SAE JA1020 … Rust coding guidelines

      \*\*Note:\*\* In general it would be ideal to purchase all annexes, errata, amendments for the listed standards.
      \*\*Note:\*\* As of writing, the latest versions of the listed standards are ISO 26262:2018, DO-178C, IEC 62304:2006, IEC 61508:2010, EN 50716:2024, IEC 60880:2006.

      \*\*Open:\*\* Should both EN 50716 and EN 50128 be bought? Same could be said for DO-178B and DO-178C, or any older version of a standard.
   5. MC/DC tool submission [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/issues/679](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/issues/679)
6. Rust Project Bridge
   1. Clippy lints identification for Rust Project Goal: [Establish a Spot for Safety-Critical Lints in Clippy](https://rust-lang.github.io/rust-project-goals/2026/safety-critical-lints-in-clippy.html)
      1. Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/SCRC.20.3C.3D.3E.20t-opsem.3A.20Normative.20Documentation.20for.20Sound.20.60unsafe.60/with/586198564) on Rust Zulip
      2. Sam: investigate lint 2 (pointer as underscore)
      3. Pete: investigate lint 3i (integer to pointer, general conversions)
      4. Pete: open an Issue for lint 1 (int as int)
      5. From this listing:
         1. No \`as\` with integers is extremely similar to existing lints (no blanket lint but a widening lint exists) e.g. \`[clippy::cast\_lossless](https://rust-lang.github.io/rust-clippy/master/index.html?search=cast_loss#cast_lossless)\` \- inexact match but demonstrates checking of \`as\`
         2. \`as\`-pointer casts is also similar to existing lints e.g. \`[clippy::ptr\_as\_ptr](https://rust-lang.github.io/rust-clippy/master/index.html?search=underscore#as_pointer_underscore)\`, \`[clippy::as\_pointer\_underscore](https://rust-lang.github.io/rust-clippy/master/index.html?search=underscore#as_pointer_underscore)\` \- inexact match
         3. Integer to pointer has some support as \`[integer-to-ptr-transmutes](https://doc.rust-lang.org/rustc/lints/listing/warn-by-default.html?highlight=int%20to%20pointer#integer-to-ptr-transmutes)\`, still only partial coverage (transmute only)
   2. Isolated, small examples of so-called “gray zones” for soundness and definedness in Eclipse iceoryx2 are being formulated within the next few weeks for the Rust Project Goal: [Normative Documentation for Sound unsafe Rust](https://rust-lang.github.io/rust-project-goals/2026/safe-unsafe-for-safety-critical.html)
      1. Register interest [here](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Getting.20involved.20with.20Clippy.20for.20SCRC.20lints/with/583090116) on Rust Zulip
   3. t-fls working to get 1.95.0 release done as a part of [Stabilize FLS Release Cadence](https://rust-lang.github.io/rust-project-goals/2026/stabilize-fls-releases.html)
      1. For more details, see recent meeting notes: [2026-06-12](https://github.com/rust-lang/fls-team/blob/main/meetings/2026-06-12.md) and [2026-06-19](https://github.com/rust-lang/fls-team/blob/main/meetings/2026-06-19.md)
   4. Pete needs to check in with Tony or Mark or others on progress towards [Implement and Maintain MC/DC Coverage Support](https://rust-lang.github.io/rust-project-goals/2026/mcdc-coverage-support.html)

## Check-in area

**Please add your name, and an emoji that describes your day.**

* Alexandru Radovici 😀
* Oreste Bernardi 🫠
* Mark Hermeling 🌲
* Manuel Hatzl
* Zalán Bálint Lévai 😀
* Stefan Akatyschew :-)
* Pete LeVasseur ☕
* Tiago Manczak

 **Notetaker:**

* Tiago Manczak

## Housekeeping section

## Tasks

* Tiago will update the criteria together with Manuel

## Meeting Minutes

* Previous meeting minutes approved and merged.
* Meeting at RustConf \- information sent by email and availability requested to be provided. Tuesday won’t be possible though.
* Tooling
  *  \- PR reviewed
    * PR 683 \- clean up
      * Same was requested to be done for coding guidelines and to liaison (Manuel Hatzl will take care)
    * PR 638
      * Merged on the fly
    * PR 685
      * Old railway standard superseded by new one
  * Rust Foundation decided to buy standards and we need to provide the list
    * List was reviewed by the participants
    * Estimated costs of the list is around U$5000
    * Prioritization and exact cost are necessary to be able to bring it to the Foundation
    * The ISO26262 will be soon updated in 2027 (unofficial information), if we buy now the might need to purchase again soon
    * The standard will be available by request with a statement of use similarly as it was done with the MISRA-C committee.
    * Idea is to get in contact with some standardization bodies to get them for free and only available under the terms specified by the tooling committee.
    * Granting access to those standards to students and developers will be a good push on contributions to safety-critical rust
  * Floyd \- [https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/issues/679](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/issues/679)
    * Open-source mc-dc coverage engine for Rust
      * Developers approach one committee member to ask about interests on using it.
      * Code looks vibe coded what raises some concerns on blindly accepting it in the list
      * Suggestion is to invite developer to explain and show the tool in one tooling committee meeting
      * Tool is also very new (\~1 month old)
        * Suggestion is to adjust the criteria to accept tools
          * \[todo\] Tiago will update the criteria together with Manuel
            * Pete will share a similar document about project acceptance from the Eclipse SDV working group
      * \[decision\] in case developer comes and present tools until next meeting we can accept if suitable, in case of no response the PR will be rejected

  * Rust Project Bridge
    * Clippy lints
      * From the coding guidelines many new clippy lints are requested to be introduces
        * More information about the activities will be added to Zulip channel
    * Unsafe Rust
      * Suggestion is to get small examples and out of the iceoryx2 that will be done by the iceoryx2 in the next couple of weeks. Out of that a document will be create as a kind of a guideline
    * t-fls
      * Version 1.95 will be released in about 3 weeks
      * Most change a bug fixes it means a change log
      * Volunteers are welcome to collaborate
    * MC/DC development
      * Adacore reported the work is in progress
      * Rust project is requesting a progress report monthly
      * No current template for that is available
      * Quarterly the project releases a summary of the Rust Project Goals
    * List of things of high value in the safe critical rust
      * Pete is working on
      * This list can be the source of future Rust projects goals and eventually funding request as well
      * It will be on the foundation google drive soon for review
      * Process how to proceed with that is still to be discussed

  * Cargo-reveal
    * Zalán is working on a project called cargo-reveal
    * cargo-reveal will translate the macros into valid rust code that can be fed to the rust compiler
    * This tool will be presented in the next meeting
