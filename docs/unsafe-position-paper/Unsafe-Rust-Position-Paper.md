# Assessing Rust's `unsafe` Code in Safety-Related Software

*Guidance for functional-safety assessors — draft v0.1, for publication by the Safety-Critical Rust Consortium.* *Applicable context: software developed in Rust and assessed under ISO 26262, IEC 61508, IEC 62304, or DO-178C. Informative guidance; not a normative standard.*

---

## 1\. Purpose and scope

This document explains what the Rust keyword `unsafe` ***does*** and ***does not*** signify, how it maps onto concepts already present in functional-safety standards, what evidence a development organization should be able to produce for it, and which findings should be raised when that evidence is absent. It is written for assessors who do not necessarily read Rust.

It does not address tool qualification for the Rust compiler or compliance with coding guidelines in general.

## 2\. The semantics of “unsafe”

The word "`unsafe`" in Rust source code is a term in the programming language and **does not assert a functional-safety property**. In other words, the term ‘unsafe’ does not imply that the associated code is unsafe. Its precise meaning is:

> *Within an* `unsafe` *region, the compiler's usual checks still apply, but the region is permitted to perform specific operations, such as raw-pointer dereferences and calls to* `unsafe` *functions, whose correctness conditions the compiler cannot verify. The developer has to responsibility to assure that this code does not have undefined behavior. If the assertion is wrong, the resulting undefined behaviour may manifest anywhere in the program, not only in the marked region.*

The `unsafe` keyword is a statement about the **boundary of automatic (tool-based) verification** — comparable in kind to a code region excluded from static-analysis or proof-tool coverage in any other language, with manual review substituted as the verification method.

Consequences the assessor should internalize before reading any Rust artifact:

1. **The presence of `unsafe` is neither a defect nor a hazard.** It marks the point at which manual verification substitutes for automatic verification. There can be multiple reasons for the use of `unsafe`. Often bare-metal Rust programs, for example, often contain `unsafe` code to handle memory-mapped I/O, interrupt configuration, DMA, and foreign-function calls into vendor SDKs.  
2. **Absence of `unsafe` is not a safety claim.** Code free of `unsafe` retains the compiler's memory-safety guarantees but can still violate functional requirements and fail.   
3. **A "zero `unsafe`" claim from a supplier warrants scrutiny, not comfort.** For embedded targets, it usually means the `unsafe` regions reside in a dependency (a hardware abstraction or vendor crate) rather than in the audited codebase. The proof obligations still exist; they have moved to code receiving less review. Ask where they went (see §6).

Recommended practice for assessment reports: refer to these regions as **manually-verified code regions** rather than "unsafe code".

It is important to keep in mind that the Rust language enforces some memory safety properties statically, and some are enforced dynamically. This means that a comprehensive test suite is still important to ensure that the software behaves as expected in all possible scenarios.

The dynamic enforcement is significant, in C or C++, in most cases memory safety is not enforced at all and unnoticed corruption can lead to problems much later and in unpredictable ways.

## 3\. The benefit of unsafe to an assessor

Rust's marker has a property legacy C or C++ code does not offer: the set of code regions requiring manual memory-safety argument is **syntactically enumerable**. The compiler rejects programs that perform the relevant operations outside a marked region. Therefore:

- The manual-verification workload is a finite, machine-extractable list, not a judgment call.  
- Partitioning claims are tool-enforceable: a crate (compilation unit) carrying the attribute `#![forbid(unsafe_code)]` provably contains no such regions, and the compiler enforces this.  
- The safety argument for memory integrity decomposes cleanly: (a) an enumerated set of reviewed manual arguments; (b) a comprehensive set suite to cover all dynamic checks.

Compared to  C or C++, the benefit is significant. The first two points provide an enumerated list of locations for manual review, while point 2 (b) ensures that, if an unsafe operation would happen during runtime, it is caught, as opposed to be allowed to propagate.


## 4\. Mapping to standards concepts

| Rust construct | Meaning | Nearest standards concept |
| :---- | :---- | :---- |
| `unsafe { … }` block | The developer manually discharges a stated invariant and needs to document the need for the unsafe block and justify why the code is correct. | Verification by review/analysis where tool verification is not applicable (e.g., ISO 26262-6 verification methods; DO-178C review & analysis objectives) |
| `unsafe fn` | Function imposes documented preconditions that the compiler cannot check; every caller must be inside a marked region | Documented interface assumption/usage constraint on a software unit |
| `unsafe trait` / `unsafe impl` | A contract attached to an interface: implementers assert compliance (the compiler cannot check it), and downstream code is entitled to assume it when reasoning about memory safety. | Safety-related interface requirement allocated to the implementing component |
| `// SAFETY:` comment | Recorded rationale for why the invariants hold at this site | Verification rationale/review record |
| `#![forbid(unsafe_code)]` | Compiler-enforced declaration that a compilation unit contains no such regions | Tool-enforced partitioning / freedom-from-interference support at the source level |
| `#[deny(unsafe_op_in_unsafe_fn)]` etc. | Lint configuration, tightening the marking discipline | Coding-guideline enforcement |

Note the contract structure: `unsafe fn` *declares* an obligation; the `unsafe` block at the call site *accepts* it. The keyword marks both sides.

## 5\. The developer’s responsibility

For each assessment involving Rust at the source level, expect:

1. **An unsafe inventory**: a complete, generated (not hand-maintained) list of all `unsafe` regions in the code under assessment *and its dependency tree*, each with location, category (MMIO, FFI, concurrency primitive, performance, …), and rationale. Tools exist to extract the raw list; the rationale is the developer's obligation.  
2. **A recorded justification per region** (`// SAFETY:` comments or equivalent traceable records), enforced by lint (`clippy::undocumented_unsafe_blocks` or a qualified equivalent) in CI, not by convention. Note that the code in an `unsafe` region could trigger problems elsewhere in the code if it violates an invariant.  
3. **Review evidence** proportionate to the integrity level: who reviewed each region, against what criteria.   
4. **A partitioning statement**: which crates are `forbid(unsafe_code)` and which are not, and whether the boundary aligns with the criticality decomposition.  
5. **Treatment of generated and third-party code.** Binding generators and vendor crates routinely emit `unsafe` regions *without* a documented rationale (as acknowledged openly by the maintainers of such tools). If generated code is in scope, the developer must state how its regions are justified — generator qualification, output review, or wrapping.  
   

## 6\. Assessment questions

- How many manually-verified regions exist in the delivered code, including dependencies? Show the generated inventory.  
- For a sample: state the invariant being asserted and show the recorded rationale and review record.  
- Why is each region necessary? Is there a safe construct that was rejected, and why?  
- Where a "no unsafe code" claim is made: at what boundary? Show the dependency-tree inventory demonstrating where the obligations actually reside, and the review regime applied there.  
- How is the marking discipline enforced (lints in CI, forbidden-by-default with justified exceptions)?  
- How are regions in *generated* code justified?  
- Has any region changed since the last assessment, and did its rationale get re-reviewed?

## 7\. Findings guidance

Raise a finding when:

- `unsafe` regions exist with no recorded rationale (missing verification evidence — same severity as an unreviewed manual-analysis result);  
- The inventory is hand-maintained or excludes dependencies;  
- "zero unsafe" is claimed in the safety-case narrative without a boundary statement (misleading safety-case claim);  
- lint enforcement is absent, so the completeness of `SAFETY` records depends on discipline alone;  
- Proof obligations were relocated into an uncontrolled dependency to satisfy an internal metric.

Do **not** raise a finding for the mere presence of `unsafe`, and do not treat region counts as a defect metric. The correct quality signal is *small, necessary, documented, and reviewed*, not *zero*.

## 8\. Common misconceptions

| Claim heard in assessments | Correction |
| :---- | :---- |
| "The code contains unsafe code, so it is not safe." | The keyword marks the tool-verification boundary; safety is argued by the accompanying manual verification, exactly as for any review-verified artifact. |
| "The code is 100% safe Rust, so it is safe." | It carries compiler memory-safety guarantees only. Functional-safety obligations are untouched. Also, verify where dependency obligations live. |
| "Unsafe count went up, quality went down." | Possibly the opposite: obligations may have surfaced from a dependency on the reviewed application code. Assess the inventory delta, not the count. |
| "The compiler is qualified, so unsafe regions are covered." | The qualification covers the compiler's guarantees for *unmarked* code. Marked regions are precisely where those guarantees stop; they are covered by the manual evidence in §5. |



