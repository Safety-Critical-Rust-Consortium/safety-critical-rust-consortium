# **Coding Guidelines Subcommittee Meeting on 2026-11-11 @ 1600 CET / 1000 EST**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-11-11&sln=10-11&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker  
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-11-04/minutes.md)  
3. Introduction of new members  
4. Mira: changes made during the MISRA C++ mapping review  
   - Mira will walk through the main changes she’s made in [PR \#1226](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226) since we started reviewing the mapping.  
   - This includes classification changes, FFI scope, and revised Rust rationales, with room for discussion on how our feedback has landed.  
5. FLS study group  
   - Update on availability in the LettuceMeet linked in the [Zulip discussion](https://rust-lang.zulipchat.com/#narrow/channel/579369-safety-critical-consortium.2Fcoding-guidelines/topic/FLS.20Study.20Group.20-.20updating.20guidelines/with/634982556) and scheduling the first session.  
6. Working session: close out the MISRA C++:2023 to Rust mapping review  
   - Parent tracking issue: [\#575](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)  
   - Documentation PR: [\#1226 Add MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)  
   - Continue from the [November 4 decision in \#1245](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1245#issuecomment-6635417192): retain external rationales for now, work toward our own Rust-specific rationales, and do not block the release solely on that rewrite.  
   - Continue the equivalence checks for **4.1.3, 5.7.1, Directive 5.7.2, 5.7.3, 6.0.2, 6.2.2, 6.4.1, and 19.3.1**, carrying over any November 4 outcomes not yet recorded inline. Capture whether each reference is sufficient for this release or a Rust-specific explanation is needed now.  
     - Start with [4.1.3](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226#discussion_r3675832409), including its classification and the dependency from Rule 8.7.1.  
   - If time permits, resolve [6.7.1](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226#discussion_r4350264105): should the restriction on persistent function-local state include safe atomics and locks?  
   - Please leave feedback inline on the relevant mapping in PR \#1226, including agreement with the proposed categorization and any required rationale changes.  
7. Round table  
   - Next working sessions: prepared batches of outstanding classifications and rationales, followed by FFI consistency across the standards appendices or trial reviews of existing draft guidelines before the incoming package.  
   - Remaining work toward coding guidelines v0.2.0.

   ## **Check-in area**

   **Please add your name, and an emoji that describes your day.**

- Pete LeVasseur ✌️  
- Mira Baumann 🚲  
- Samuel Wright 🥁  
- Max Jacinto 😵‍💫  
- Arnaud Riess ⚙️  
- Oreste Bernardi 🌧️  
- Achim Kriso 🦆  
- Arthur Hicken 🙃   
- Mario Mottl 🐣  
- xx  
- xx  
- xx  
- Xx  
- xx

  **Notetaker:**

- Max Jacinto

  For tips on how we take notes in the Safety-Critical Rust Consortium, please see the [Meeting Notetaker Role](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/docs/notetaker-role.md) doc.

  ## **Housekeeping section**

- Document space: [coding-guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/tree/main/subcommittee/coding-guidelines)  
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)  
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)  
- [`contributor experience` view](https://github.com/orgs/rustfoundation/projects/1/views/4)  
- [`coding guideline` view](https://github.com/orgs/rustfoundation/projects/1/views/5)

  ## **Meeting Minutes**

- **\[Introduction of new members\]**  
  - Introduction of new member: Interested in automotive; sent to the Consortium by their company to help out with the project. Thank you and welcome\!  
- **\[Review of changes introduced after MISRA C++ review\]**  
  - Checks of GitHub tags in comments such as “Outdated”; GitHub’s comment section may not be the best tool to check comments due to how uncomfortable the experience is when it comes to reviewing large batches of comments, especially since some can get lost and there’s no proper way to organize them.  
  - Initiative to deploy an LLM to try and clean up the comments, but will be in revision since the changes are soon-to-be merged.  
    - Another proposal is that once this is merged, we could create a branch with a new PR with checkboxes for the things left to review (around 7).  
- **\[FLS Study Group\]**  
  - Review of the Lettuce Meet schedules.  
  - Proposal to meet on Friday 13th of November and then try to schedule regular monthly meetings.  
  - **\[Important Point to Review\]** Discuss if UB rules are under consideration of the FLS.  
  - **\[Action Item\]** Talk with the people working on the Rust Specification as a way to try and to bridge these gaps  
- **\[Working Session\]**  
  - Rule 4.1.3: Applicable to Rust BUT we have to give a clear rationale as to why it’s applicable.  
    - Even if we’re using safe Rust we still have to be careful with UB\! Especially if we use unsafe functions that can call C/C++ code.  
    - We can write something akin to “It is applicable BUT in practice UB in safe Rust is considered as a compiler bug”. We still have to be careful with this phrasing in cases such as getting a security certification.  
    - This has spawned the creation of a new issue in the repo regarding what compiler bugs should be considered by the Consortium when it comes to UB. We’ll focus specifically on the specification of the language itself.  
  - Rule 5.7.1: Agreement of previous consensus regarding the rule.  
  - Dir 5.7.2: Previously discussed too; code used for documentation and examples should not be considered as “commented out” (such as the use of \`doctest\`).  
  - Rule 5.7.3: Previously agreed that it doesn’t map to either safe or unsafe Rust; no expanded rationale given, but something simple can be said from our part such as “Rust has no line splicing”.  
  - Rule 6.0.2: Previously agreed that the rule is not applicable to Rust.  
  - Rule 6.2.2: Agreed that previous consensus regarding the rule was correct.   
  - Rule 6.4.1: Agreed that previous consensus of it being applicable to both safe and unsafe Rust was correct; no extra comments.  
  - Rule 19.3.1: `stringify` is a special case where trusting in its (bytes) output is not 100% recommended. **\[Action Item\]** It is recommended to open up an issue about it\!

  ## **Material**

  Meeting-specific reading:

- [November 4 meeting minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-11-04/minutes.md)  
- [November 4 rationale decision in \#1245](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1245#issuecomment-6635417192)  
- [MISRA C++ mapping proposed in PR \#1226](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files)  
- [MISRA C:2025 Addendum 6](https://misra.org.uk/app/uploads/2025/03/MISRA-C-2025-ADD6.pdf) and [our MISRA C mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/blob/main/src/appendices/standards-matrices/misra-c-2025-mapping.rst)  
- [FLS Audit Guide](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/blob/main/docs/fls-audit.md)
