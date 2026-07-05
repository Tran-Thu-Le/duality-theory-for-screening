---
name: narrative-summary
description: Locked narrative positioning plus per-file narrative recap for doc1/doc2/doc3, checked against the actual .tex content.
metadata:
  type: reference
---

# Paper Narrative Summary

Snapshot as of 2026-07-05, synced against the current
`doc2-universe.tex` and `doc3-screening.tex` (duality now a third
transformation, with three framework laws: Involution, Translation
Duality, Restriction Duality, replacing the old Fenchel
Equivariance/Commutativity pair). For the full notation/dependency
tables, see `paper.md`; this file is the narrative companion, what
story each file/section tells, and how heavily each result should be
narrated.

## Title

> **Toward a Duality Theory for Feature and Sample Screening**

Already set in `meta/data.tex`. The title promises exactly one thing,
a duality theory, not a framework, not a group action, not a calculus.
Those are means.

## Central Narrative

> This paper gives a mathematical formulation of the apparent duality
> between feature screening and sample screening.

The framework exists only to prove this sentence. It is not a second,
competing narrative.

---

## Section 1 — Introduction

**Role:** pose the question. Resolve nothing technical. `doc1-intro.tex`
is one continuous sequence of paragraphs under a single
`\section{Introduction}`, no `\subsection` anywhere. This entry was not
re-verified in the 2026-07-05 doc2/doc3 sync; see `paper.md`'s TODO.

```
Background: Screening in ML + Historical development
      │
      ▼
The Gap: both exploit convex duality, but each is model-specific,
derived case-by-case, no common mathematical language
      │
      ▼
Main Question (plain quote block, not boxed)
      │
      ▼
Positioning Sentence: the goal is to formulate the duality, not argue it
      │
      ▼
Main Insight: common representation level, duality intertwines the two
      │
      ▼
Why is this difficult? (primal fixed point vs. dual Fenchel–Young
identity look unrelated)
      │
      ▼
Our Approach: representation framework (proof strategy, not a
contribution)
      │
      ▼
Main Theorem: Feature ↔ Sample Duality (words → formula → diagram)
      │
      ▼
Why does it matter? (consequences named, not detailed)
      │
      ▼
Contributions
```

Three-sentence test (doc1's own opening paragraph): (1) ML has two
screening paradigms; (2) both exploit convex duality, but each has been
derived in a model-specific, case-by-case manner, with no common
mathematical language relating them; (3) this paper proves they are
Fenchel-dual manifestations of the same underlying operation via a
representation framework in which screening decomposes into
translation and restriction.

---

## Section 2 — FR Representations and Transformations

(`docs-new/doc2-universe.tex`, `\label{sec:operators}`.)

**Role: this section does not study screening. It constructs the
mathematical universe in which screening will later be defined.** Do
not sell results as screening contributions.

```
§2.1 FR representations (object)
      │
      ▼
§2.2 Duality — law: Involution
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
- **§2.2 Duality:** the FR dual `p^*=(g^*,f^*,-A^T,-a)`; the remark
  that `*: Γ → Γ` is a transformation exchanging the roles of `f`/`g`
  and of domain/slope translation. **Law: Involution**, `(p^*)^*=p`,
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

**Role:** this is where the paper scores its points. No "Consequences"
subsection: each corollary is narrated immediately after the result
that produces it.

```
3.1  Definitions (S^F, S^S)
       ↓
       Corollary: Intrinsic Complexity Reduction

3.2  Decomposition (structural theorem)
       ↓

3.3  Duality (MAIN theorem)
       ↓
       Corollary: Simultaneous Screening
```

Doc3's own opening paragraph frames this as two main results
(Decomposition, Duality) plus, as a by-product, intrinsic complexity
reduction and simultaneous screening, matching this tiering.

- **Main theorem:** Feature–Sample Duality, `(S^F(p))^*=S^S(p^*)`.
  Its proof combines Decomposition with Translation Duality and
  Restriction Duality (doc2) as three explicit steps, plus two
  convex-analysis facts stated inline.
- **Structural theorem:** Decomposition, `S=R∘T`.
- **Corollaries:** Intrinsic Complexity Reduction (§3.1), Simultaneous
  Screening (§3.3, needs Duality applied twice and Involution).

---

## Hierarchy of the Whole Paper

```
TITLE
Toward a Duality Theory for Feature and Sample Screening
│
├── Central Narrative
│      This paper gives a mathematical formulation of the apparent
│      duality between feature screening and sample screening.
│
├── Section 1 — Introduction
│      Role: pose the question
│
├── Section 2 — FR Representations and Transformations
│      Role: construct the mathematical universe (not screening)
│      Laws: Involution (duality), Translation Duality (translation),
│      Restriction Duality (restriction)
│
└── Section 3 — Duality of Feature and Sample Screening
       Role: score the paper's points
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
| Framework law (duality) | Involution | 2.2 | — |
| Framework law (translation) | Translation Duality | 2.3 | — |
| Framework law (restriction) | Restriction Duality | 2.4 | — |
| Structural theorem | Decomposition | 3.2 | — |
| Corollary | Intrinsic Complexity Reduction | 3.1 | Definitions, same subsection |
| Corollary | Simultaneous Screening | 3.3 | Duality, same subsection |

No "Theorem 1/2/3" numbering; results named by role.

---

## doc2-universe.tex — narrative recap

Constructs the mathematical universe screening will later be defined
in: FR representations, and three transformations (duality,
translation, restriction), each with its own structural law. Flow:
**§2.1 FR Representations** (closed/proper/convex regularity; problem
size `size(p):=(m,n)`; classes `Γ_{m,n}`, `Γ`; closure justifying `a`)
→ **§2.2 Duality** (`p^*=(g^*,f^*,-A^T,-a)`; Involution `(p^*)^*=p`
with proof) → **§2.3 Translation** (primitive translations merged into
one Definition; translation and its dual parameter merged into one
Definition; Translation Duality theorem, full proof) → **§2.4
Restriction** (`R^F_I`,`R^S_J`, explicitly typed; Restriction Duality,
full proof). No closing/Summary subsection; ends with Restriction
Duality's usage note.

**Naming history worth remembering:** "Fenchel Equivariance" was
renamed "Translation Duality," and the old "Commutativity" proposition
was dropped entirely and replaced by "Restriction Duality," a
different, proved claim (same index set, dualizes to the other
restriction type) rather than an assertion that `R^F` and `R^S`
commute. Both renames and the drop are final; do not reintroduce the
old names.

## doc3-screening.tex — narrative recap

Defines feature and sample screening from optimization assumptions (not
from the translation/restriction formula), illustrates each with a
worked example (Lasso for feature screening, soft-margin SVM for
sample screening, both framed as the `z=0`/`s=0` special case of the
general operator, with a footnote to `ogawa2013` for the SVM case's
general subgradient condition), states Intrinsic Complexity Reduction
immediately from the definitions, then discovers, as theorems, that
both screening operators decompose into Section 2's primitives
(Decomposition) and are Fenchel-dual (Duality, the main result, proved
by combining Decomposition with Translation Duality and Restriction
Duality as three explicit steps), with Simultaneous Screening falling
out as a corollary of Duality applied twice plus Involution.

**Known open item:** doc3's opening paragraph uses `p ∈ Γ_{m,n}`
(matching doc2), but `cor:complexity`, `thm:duality`, and
`cor:simultaneous` still write `p ∈ mathcal{FR}^{sep}_{m,n}`, undefined
anywhere in the current text. See `paper.md`'s TODO.

## doc1-intro.tex — narrative recap

Not re-verified in the 2026-07-05 doc2/doc3 sync (that pass
prioritized doc2/doc3 per the author's request). Last known state: one
continuous sequence of paragraphs under a single `\section{Introduction}`,
no `\subsection`, ending with the Main Theorem presented as
transition → formula → plain-language restatement → commutative
diagram. Re-verify directly against the file before relying on exact
wording here.

## Known inconsistency outside doc1/doc2/doc3 (flagging only)

`meta/data.tex`'s `\paperAbstract` still claims "we further show that
the two screening operators commute," the exact claim that was found
false and replaced by Simultaneous Screening. Not fixed in this pass;
logged in `paper.md`'s TODO.
