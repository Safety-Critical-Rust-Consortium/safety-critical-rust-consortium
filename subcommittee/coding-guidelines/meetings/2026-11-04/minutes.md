# **Coding Guidelines Subcommittee Meeting on 2026-11-04 @ 1600 CET / 1000 EST**

[Link](https://www.worldtimebuddy.com/?qm=1&lid=5,12,2643743,8,1850147,100,14,14,1835848,1816670&h=5&date=2026-11-04&sln=10-11&hf=1) to meeting time in common time zones.

| Search Key | Description |
| :---- | :---- |
| todo | Action Item |
| decision | Something decided on |
| important | Key information |

## **Agenda**

1. Solicitation of notetaker  
2. Acceptance of [Previous Meeting Minutes](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/subcommittee/coding-guidelines/meetings/2026-10-30/minutes.md)  
3. Introduction of new members  
4. FLS study group  
   - Please add your availability for the first session during the week of 2026-11-09 to the LettuceMeet linked in the [Zulip discussion](https://rust-lang.zulipchat.com/#narrow/channel/579369-safety-critical-consortium.2Fcoding-guidelines/topic/FLS.20Study.20Group.20-.20updating.20guidelines/with/634982556).  
5. Working session: continue reviewing the MISRA C++:2023 to Rust coding guidelines mapping  
   - Parent tracking issue: [\#575](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/575)  
   - Documentation PR: [\#1226 Add MISRA C++ mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226)  
   - [**Rationale policy — \#1245**](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1245)**: may a standards mapping rely on an external applicability assessment without its own Rust-specific explanation?** Use MISRA C++ → MISRA C:2025 ADD6 as the worked case.  
     - **If yes:** identify the source standard, version, rule and assessment; verify equivalent scope and explain differences in applicability.  
     - **If no:** require a brief Rust-specific explanation, reusing existing guideline rationales where appropriate. External references may still support it.  
     - **Either outcome:** record the meeting’s decision in \#1245, including the follow-up to document a shared **Mapping rationale policy** on the [Standards Matrices page](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/blob/main/src/appendices/standards-matrices/index.rst) and track alignment of existing mappings.  
     - Apply the decision to [Rule 19.3.2 / MISRA C Rule 20.11](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226#discussion_r4402047515), then work through this **initial MISRA C++ alignment batch**. Other mappings still need assessment against the policy. Preserve agreed classifications unless a substantive discrepancy is found.  
     - **Reference only (9):** [0.0.1](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files#diff-975beac416dcf5a5e8e57f2ba2743a05cb3906f0eb77821199f53d9c65f23e64R28), [0.0.2](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files#diff-975beac416dcf5a5e8e57f2ba2743a05cb3906f0eb77821199f53d9c65f23e64R33), [0.1.1](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files#diff-975beac416dcf5a5e8e57f2ba2743a05cb3906f0eb77821199f53d9c65f23e64R38), [0.2.2](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files#diff-975beac416dcf5a5e8e57f2ba2743a05cb3906f0eb77821199f53d9c65f23e64R53), [0.2.3](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files#diff-975beac416dcf5a5e8e57f2ba2743a05cb3906f0eb77821199f53d9c65f23e64R58), [5.7.3](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files#diff-975beac416dcf5a5e8e57f2ba2743a05cb3906f0eb77821199f53d9c65f23e64R652), [6.0.2](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files#diff-975beac416dcf5a5e8e57f2ba2743a05cb3906f0eb77821199f53d9c65f23e64R679), [6.4.1](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files#diff-975beac416dcf5a5e8e57f2ba2743a05cb3906f0eb77821199f53d9c65f23e64R127), [19.3.2](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files#diff-975beac416dcf5a5e8e57f2ba2743a05cb3906f0eb77821199f53d9c65f23e64R866).  
     - **Reference plus commentary (6):** [0.2.1](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files#diff-975beac416dcf5a5e8e57f2ba2743a05cb3906f0eb77821199f53d9c65f23e64R48), [4.1.3](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files#diff-975beac416dcf5a5e8e57f2ba2743a05cb3906f0eb77821199f53d9c65f23e64R88), [5.7.1](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files#diff-975beac416dcf5a5e8e57f2ba2743a05cb3906f0eb77821199f53d9c65f23e64R93), [Directive 5.7.2](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files#diff-975beac416dcf5a5e8e57f2ba2743a05cb3906f0eb77821199f53d9c65f23e64R98), [6.2.2](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files#diff-975beac416dcf5a5e8e57f2ba2743a05cb3906f0eb77821199f53d9c65f23e64R398), [19.3.1](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files#diff-975beac416dcf5a5e8e57f2ba2743a05cb3906f0eb77821199f53d9c65f23e64R863).  
     - Checks to carry through: [19.3.1 already has an October 28 decision to make it applicable](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226#discussion_r4401938844); 4.1.3 still questions its classification, and [8.7.1](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files#diff-975beac416dcf5a5e8e57f2ba2743a05cb3906f0eb77821199f53d9c65f23e64R533) relies on it.  
     - If the policy remains unresolved, record the specific question and evidence needed.  
   - **If time permits:**  
     - [Rule 28.6.1](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226#discussion_r4456487416): is unintended copying through conversions a direct mapping, or a separate Rust guideline candidate?  
     - [Rule 6.7.1](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226#discussion_r4272362493): should the restriction on persistent function-local state include safe atomics and locks?  
   - *Please leave feedback inline on the relevant mapping in PR \#1226, including agreement with the proposed categorization.*  
6. Round table  
   - Remaining work toward coding guidelines v0.2.0.

   ## **Check-in area**

   **Please add your name, and an emoji that describes your day.**

- Douglas Deslauriers 🗳️  
- Oreste Bernardi 🧥  
- Mira Baumann 🔊  
- K Wayne Lee 😴  
- Mark Hermeling (first 30 mins only) 😎  
- Achim Kriso 🦆  
- Arthur Hicken   

  **Notetaker:**

- Mira

  For tips on how we take notes in the Safety-Critical Rust Consortium, please see the [Meeting Notetaker Role](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/blob/main/docs/notetaker-role.md) doc.

  ## **Housekeeping section**

- Document space: [coding-guidelines](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-consortium/tree/main/subcommittee/coding-guidelines)  
- Zulip: [safety-critical-consortium: Coding Guidelines](https://rust-lang.zulipchat.com/#narrow/channel/445688-safety-critical-consortium/topic/Coding.20Guidelines)  
- [Kanban board](https://github.com/orgs/rustfoundation/projects/1/views/3)  
- [`contributor experience` view](https://github.com/orgs/rustfoundation/projects/1/views/4)  
- [`coding guideline` view](https://github.com/orgs/rustfoundation/projects/1/views/5)

  ## **Meeting Minutes**

- Previous Meeting Minutes accepted  
- Discussion on [Issue 1245](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/issues/1245)  
  - Agreement that we probably should have our own rationales at some point  
  - Discussion on maybe deferring that to a later release  
  - There are around 15 rules that currently defer to the MISRA C document  
  - decision: Keep them for now. Try to write our own rationales for them, but do the release even if the new rationale hasn’t been written yet  
  - looking at those 15 to make sure the C++ and C rules are equivalent

  ## **Material**

  Meeting-specific reading:

- [MISRA C++ mapping proposed in PR \#1226](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/pull/1226/files)  
- [MISRA C:2025 Addendum 6](https://misra.org.uk/app/uploads/2025/03/MISRA-C-2025-ADD6.pdf) and [our MISRA C mapping](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/blob/main/src/appendices/standards-matrices/misra-c-2025-mapping.rst)  
- [FLS Audit Guide](https://github.com/Safety-Critical-Rust-Consortium/safety-critical-rust-coding-guidelines/blob/main/docs/fls-audit.md)

