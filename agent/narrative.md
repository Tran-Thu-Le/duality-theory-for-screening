---
name: narrative-summary
description: Locked narrative positioning plus per-file narrative recap for doc1/doc2/doc3, checked against the actual .tex content.
metadata:
  type: reference
---

# Paper Narrative Summary

Snapshot as of 2026-07-05, synced against the current `doc1-intro.tex`,
`doc2-universe.tex`, `doc3-screening.tex`, and `meta/data.tex`. For the
full notation/dependency tables and a list of open questions for the
author, see `paper.md`; this file is the narrative companion, what
story each file/section tells, and how heavily each result should be
narrated.

## Title

> **Toward a Duality Theory for Feature and Sample Screening**

Already set in `meta/data.tex`. The title promises exactly one thing,
a duality theory, not a framework, not a group action, not a calculus.
Those are means.

## Central Narrative

> Screening is equivariant under Fenchel–Rockafellar duality: feature
> screening and sample screening are the same transformation, read on
> a primal and on its dual FR representation.

The framework exists only to prove this. It is not a second, competing
narrative. This is the vocabulary the abstract and the current
introduction both use directly ("equivariant" appears in-text, not
only in this summary).

---

## Section 1 — Introduction

**Role:** pose the paper's two questions. Resolve nothing technical
until the FR-representation language is in hand. `doc1-intro.tex` is
one continuous sequence of paragraphs under a single
`\section{Introduction}`, no `\subsection` anywhere.

```
Context: screening reduces cost in large-scale convex optimization
      │
      ▼
Classification: safe vs. unsafe; static/dynamic/sequential;
tighter safe regions; generalizations (squeezing, relaxing, peeling)
      │
      ▼
Scope: this paper's axis is feature vs. sample; its level is
structural theory, not safety
      │
      ▼
Historical development: Lasso (feature) → SVM dual (sample, by
transferring the feature-screening philosophy) → parallel evolution →
simultaneous screening → FR-duality-based frameworks
      │
      ▼
Tension and gap: suggestive relationship, never formalized; each
derivation is model-specific
      │
      ▼
Boxed Q1 + Q2: model-independent formulation? if so, dual how?
      │
      ▼
Central idea: answers Q1 — a common class of representations is
needed before duality and screening can be compared directly
      │
      ▼
Class of problems / Class of objects: the FR quadruple, Γ, closure;
feature and sample screening restated as assumptions on p
      │
      ▼
Structural insight: screening is not primitive — decomposes into
translation then restriction, both equivariant under FR duality
      │
      ▼
Answer to Q2: (S^F(p))^*=S^S(p^*), then the commutative diagram
      │
      ▼
Contributions (two) → Organization
```

There is no longer a separate, explicitly labeled Positioning Sentence
paragraph ("the goal of this paper is not to argue... but to
formulate...") anywhere in the current draft — confirmed by the author
(2026-07-05) as an intentional, final drop; do not reintroduce it.
Likewise, "Why Is This Difficult?" and "Why Does It Matter?" are no
longer separate named beats; their content is folded into "Structural
insight" and "Answer to Q2" / "Contributions."

Citations introduced in this section: `elghaoui2010`,
`tibshirani2012strong`, `fan2018sure`, `bonnefoy2014dynamic`,
`wang2013lasso`, `tran2022beyond`, `dai2012ellipsoid`,
`elvira2020safe`, `guyard2022screen`, `guyard2023safe`,
`elghaoui2010safe`, `ogawa2014sample`, `shibagaki2016simultaneous`,
`ndiaye2017gap`, `yamada2021dynamic`, `tran2025one`, `wang2014safe`,
`chen2020safe`, `dantas2021safe`, `zhai2020safe`, `nguyen2026gap`. All
verified present in `meta/refs.bib`.

---

## Section 2 — FR Representations and Equivariant Transformations

(`docs-new/doc2-universe.tex`, `\label{sec:operators}`; section title
now includes "Equivariant.")

**Role: this section does not study screening. It constructs the
mathematical universe in which screening will later be defined.** Do
not sell results as screening contributions.

```
§2.1 FR representations (object)
      │
      ▼
§2.2 FR Duality — Fenchel conjugate (plain prose) then FR dual;
      law: Involution
      │
      ▼
§2.3 Translation — law: Translation Duality
      │
      ▼
§2.4 Restriction — law: Restriction Duality
```

Four subsections, one object and three transformations, each with a
single role and a single law:

- **§2.1 FR Representations:** the object `p=(f,g,A,a)`, problem size
  `size(p):=(m,n)`, separability, the classes `Γ_{m,n}` and `Γ`, and
  the closure payoff: this class is closed under all three
  transformations studied in the section, duality, translation, and
  restriction, which is why the constant `a` exists.
- **§2.2 FR Duality** (renamed from "Duality"): opens with a
  plain-prose paragraph on the Fenchel conjugate `h^*` and
  biconjugation `h^{**}=h`, not a `\begin{definition}` (author's
  choice), then the FR dual `p^*=(g^*,f^*,-A^T,-a)`; the remark that
  `*: Γ → Γ` is a transformation exchanging the roles of `f`/`g` and
  of domain/slope translation. **Law: Involution**, `(p^*)^*=p`,
  proved, duality's own structural law.
- **§2.3 Translation:** the three primitive translations
  (`T^d`,`T^v`,`T^s`, one merged Definition), then one merged
  Definition for the translation `T_k` together with its dual parameter
  `k^*`; the Abelian translation-action fact kept as informal prose,
  not a proposition; the three-part conjugate identity for primitive
  translations. **Law: Translation Duality**, `(T_k(p))^*=T_{k^*}(p^*)`,
  proved, cited by name in doc3's Duality theorem.
- **§2.4 Restriction:** index notation, one merged Definition for
  feature restriction `R^F_I` and sample restriction `R^S_J`, with
  explicit domain/codomain typing. **Law: Restriction Duality**,
  `(R^F_I(p))^*=R^S_I(p^*)` (symmetrically), proved, cited by name in
  doc3's Duality theorem.
- **Everything except the three laws is machinery:** none of it is
  sold as a contribution in its own right; it exists so Section 3's
  main theorem goes through.

Doc2 ends right after Restriction Duality's usage note; there is no
separate closing/Summary subsection, and no Commutativity result
anywhere in the file.

---

## Section 3 — Duality of Feature and Sample Screening

(`docs-new/doc3-screening.tex`, `\label{sec:screening}`.)

**Role:** this is where the paper scores its points, and where Q2 gets
its full technical answer. No "Consequences" subsection: each
corollary is narrated immediately after the result that produces it.

```
3.1  Feature and Sample Screening as Operators (S^F, S^S)
       ↓
       Corollary: Intrinsic Complexity Reduction

3.2  Decomposition of Screening (structural theorem)
       ↓

3.3  Duality of Screening (main theorem, answers Q2)
       ↓
       Corollary: Simultaneous Screening
```

Doc3's own opening paragraph frames this as two main results
(Decomposition, Duality) plus, as a by-product, intrinsic complexity
reduction and simultaneous screening, matching this tiering.

- **Main theorem:** Feature–Sample Duality, `(S^F(p))^*=S^S(p^*)`.
  Its proof combines Decomposition with Translation Duality and
  Restriction Duality (doc2) as three explicit steps, plus two
  convex-analysis facts stated inline. The Interpretation paragraph
  after the proof carries the commutative diagram.
- **Structural theorem:** Decomposition, `S=R∘T`. Its own closing
  remark now correctly credits both Translation Duality and Restriction
  Duality (fixed 2026-07-05).
- **Corollaries:** Intrinsic Complexity Reduction (§3.1), Simultaneous
  Screening (§3.3, needs Duality applied twice and Involution).

---

## Hierarchy of the Whole Paper

```
TITLE
Toward a Duality Theory for Feature and Sample Screening
│
├── Central Narrative
│      Screening is equivariant under Fenchel–Rockafellar duality.
│
├── Section 1 — Introduction
│      Role: pose Q1 (model-independent formulation?) and
│      Q2 (dual in what sense?)
│
├── Section 2 — FR Representations and Equivariant Transformations
│      Role: construct the mathematical universe (not screening)
│      Laws: Involution (FR duality), Translation Duality
│      (translation), Restriction Duality (restriction)
│
└── Section 3 — Duality of Feature and Sample Screening
       Role: score the paper's points, answer Q2 in full
       No "Consequences" subsection — corollaries attach locally
           │
           ├── 3.1 Definitions (Feature/Sample screening)
           │      └── Corollary: Intrinsic Complexity Reduction
           │
           ├── 3.2 Structural theorem: Decomposition
           │
           └── 3.3 Main theorem: Feature–Sample Duality
                  └── Corollary: Simultaneous Screening
```

## Result Tiers (do not narrate as co-equal)

| Tier | Result | Section | Attaches to |
|---|---|---|---|
| Main result of the paper | Feature–Sample Duality | 3.3 | — |
| Framework law (FR duality) | Involution | 2.2 | — |
| Framework law (translation) | Translation Duality | 2.3 | — |
| Framework law (restriction) | Restriction Duality | 2.4 | — |
| Structural theorem | Decomposition | 3.2 | — |
| Corollary | Intrinsic Complexity Reduction | 3.1 | Definitions, same subsection |
| Corollary | Simultaneous Screening | 3.3 | Duality, same subsection |

No "Theorem 1/2/3" numbering; results named by role.

---

## doc2-universe.tex — narrative recap

Constructs the mathematical universe screening will later be defined
in: FR representations, and three transformations (FR duality,
translation, restriction), each with its own structural law. Flow:
**§2.1 FR Representations** (closed/proper/convex regularity; problem
size `size(p):=(m,n)`; classes `Γ_{m,n}`, `Γ`; closure justifying `a`)
→ **§2.2 FR Duality** (plain-prose Fenchel conjugate paragraph;
`p^*=(g^*,f^*,-A^T,-a)`; Involution `(p^*)^*=p` with proof) → **§2.3
Translation** (primitive translations merged into one Definition;
translation and its dual parameter merged into one Definition;
Translation Duality theorem, full proof) → **§2.4 Restriction**
(`R^F_I`,`R^S_J`, explicitly typed; Restriction Duality, full proof).
No closing/Summary subsection; ends with Restriction Duality's usage
note.

**Naming history worth remembering:** "Fenchel Equivariance" was
renamed "Translation Duality"; the old "Commutativity" proposition was
dropped entirely and replaced by "Restriction Duality," a different,
proved claim (same index set, dualizes to the other restriction type)
rather than an assertion that `R^F` and `R^S` commute; the subsection
"Duality" was later renamed "FR Duality." All renames and the drop are
final; do not reintroduce the old names.

## doc3-screening.tex — narrative recap

Defines feature and sample screening from optimization assumptions (not
from the translation/restriction formula), illustrates each with a
worked example (Lasso for feature screening, soft-margin SVM for
sample screening, both framed as the `z=0`/`s=0` special case of the
general operator, with a footnote to `ogawa2013` for the SVM case's
general subgradient condition), states Intrinsic Complexity Reduction
immediately from the definitions, then discovers, as theorems, that
both screening operators decompose into Section 2's primitives
(Decomposition) and are Fenchel-dual (Duality, the main result,
answering Q2, proved by combining Decomposition with Translation
Duality and Restriction Duality as three explicit steps), with
Simultaneous Screening falling out as a corollary of Duality applied
twice plus Involution. The Duality subsection's closing Interpretation
paragraph carries the commutative diagram.

The Decomposition subsection's closing remark was fixed 2026-07-05
(text-only) to credit both Translation Duality and Restriction
Duality, matching `thm:duality`'s actual proof.

## doc1-intro.tex — narrative recap

Verified 2026-07-05 against the current file. One continuous sequence
of paragraphs under a single `\section{Introduction}`, no
`\subsection`, following the flow diagrammed above, ending with the
Main Theorem presented as transition → formula → plain-language
restatement → commutative diagram, matching `paper.md`'s Main Theorem
Presentation order. Two structural changes from earlier passes are
confirmed final by the author (2026-07-05): the Positioning Sentence
paragraph is gone, and the single Main Question became two (Q1, Q2).

## meta/data.tex — abstract recap

Verified 2026-07-05: the abstract no longer claims the two screening
operators commute (the earlier, false claim is gone). It now opens
with feature/sample screening motivation, states that FR
representations carry both screening and FR duality as transformations,
and states the equivariance result directly, matching Section 1's own
vocabulary. No known inconsistency remains between the abstract and
doc1/doc2/doc3.
