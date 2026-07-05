---
name: narrative-summary
description: Locked narrative positioning (2026-07-04, synced 2026-07-05) plus per-file narrative recap for doc1/doc2/doc3, checked against the actual .tex content.
metadata:
  type: reference
---

# Paper Narrative Summary

Snapshot as of 2026-07-05 (synced against doc1's historical-accuracy
revision and doc2's rename/restructuring to `doc2-universe.tex`). The
positioning below is **locked**: it is
the reference framing for every later revision. For the full
notation/dependency tables, see `paper.md`; this file is the narrative
companion — what story each file/section tells, and how heavily each
result should be narrated.

## Title

> **Toward a Duality Theory for Feature and Sample Screening**

Already set in `meta/data.tex`. The title promises exactly one thing —
a duality theory — not a framework, not a group action, not a calculus.
Those are means.

## Central Narrative

One sentence. Every subsection of every section exists to set it up,
prove it, or draw a consequence from it:

> **Feature screening and sample screening are not independent
> techniques but Fenchel-dual manifestations of the same mathematical
> structure.**

The framework exists only to prove this sentence. It is not a second,
competing narrative.

---

## Section 1 — Introduction

**Role:** pose the question. Resolve nothing technical. **Revised
2026-07-05: leads with screening/ML, not with Fenchel calculus** —
Fenchel duality's narrative weight deliberately cut back relative to
earlier drafts (it is background fact about existing methods, not the
subject of the paper). **Prose pass, same day: written out in full and
no longer split into subsections** — `doc1-intro.tex` is now one
continuous sequence of paragraphs under a single
`\section{Introduction}`; the diagram below is the logical order of
that prose, not a list of literal headers.

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
Main Insight: same operation, viewed through duality
      │
      ▼
Why is this difficult? (primal fixed point vs. dual Fenchel–Young
identity look unrelated)
      │
      ▼
Our Approach: representation framework (proof strategy, not a
contribution) — FR model + both screening formulas + dual-certificate
interpretation now live here
      │
      ▼
Main Theorem: Feature ↔ Sample Duality
      │
      ▼
Why does it matter? (consequences named, not detailed)
      │
      ▼
Contributions
```

**Three-sentence test** (doc1's own opening paragraph, the anchor for
every paragraph in Section 1, **synced 2026-07-05 to the historical-
accuracy revision**): (1) ML has two screening paradigms; (2) both
exploit convex duality, but each has been derived in a model-specific,
case-by-case manner, with no common mathematical language relating
them; (3) this paper proves they are Fenchel-dual manifestations of the
same underlying operation via a representation framework in which
screening decomposes into translation and restriction. If a reader can
summarize the paper in exactly these three sentences, the narrative
has *not* drifted back to "a paper about Fenchel calculus."

`docs-new/doc1-intro.tex`'s actual paragraph order (no subsections):
Background (two paragraphs: "Screening in machine learning,"
"Historical development") → The Gap (Main Question as a plain `quote`
block: *"Is there a common mathematical framework that explains these
seemingly different formulations?"*) → Main Insight → Why Is This
Difficult? → Our Approach (folds in the old standalone "FR
Model," "Feature Screening," and "Sample Screening" content, plus a
new "Connection to dual certificates" paragraph — none of this is
previewed before the gap is even stated) → Main Theorem → Why Does It
Matter? → Main Contributions → Organization.

---

## Section 2 — Fenchel–Rockafellar Representations and Their Transformations

(`docs-new/doc2-universe.tex`, renamed from `doc2-group.tex`; `.tex`
section title matches the locked title exactly, confirmed 2026-07-05.
`main.tex`'s `\input` updated to match.)

**Role (locked 2026-07-05): this section does not study screening. It
constructs the mathematical universe in which screening will later be
defined.** Do not sell results as screening contributions.

```
§2.1 FR representations (object)
      │
      ▼
§2.2 Translation — law: Fenchel Equivariance
      │
      ▼
§2.3 Restriction — law: Commutativity
```

Exactly 3 subsections now (confirmed against the actual file), not a
flat list of definitions:

- **§2.1 Fenchel–Rockafellar Representations:** the object, problem
  size, separability, and the payoff — an "Insight: a closed universe,
  not just a notation" paragraph explaining why the constant `a` exists
  (closure under translation and restriction).
- **§2.2 Translation of FR Representations:** the three primitive
  translations (`T^d`,`T^v`,`T^s`, one merged Definition environment),
  the translation action `T_k`, the Fenchel dual, Involution
  (proposition + proof), the dual translation `k^*`, and **Fenchel
  Equivariance** (`(T_k(p))^*=T_{k^*}(p^*)`, full proof) — the main
  theorem of the section, and the only one narrated as a result.
- **§2.3 Restriction of FR Representations:** feature/sample
  restriction, **Commutativity** (`R^F_IR^S_J=R^S_JR^F_I` — still
  stated without proof, by author instruction), restriction
  compatible with translation (also unproven), and the two technical
  lemmas Section 3 needs (Conjugate of a separable restriction,
  Separable sums preserve regularity). Ends with the locked closing
  paragraph (no separate Summary subsection).
- **Everything except the two laws is machinery:** none of it is sold
  as a contribution in its own right; it exists so Section 3's main
  theorem goes through.

---

## Section 3 — Duality Theory

(`docs-new/doc3-screening.tex`; `.tex` section title already "Duality
of Feature and Sample Screening" — matches this positioning as-is.)

**Role:** this is where the paper scores its points. **No
"Consequences" subsection** (author's call, 2026-07-04): the section is
narrated by logical dependency, not by grouping results of the same
type. Each corollary is a child of the result that produces it, not a
sibling of a shared final stage:

```
3.1  Definition (S^F, S^S)
       ↓
       Corollary: Intrinsic Complexity Reduction

3.2  Decomposition (structural theorem)
       ↓

3.3  Duality (MAIN theorem)
       ↓
       Corollary: Simultaneous Screening
```

Definition produces its corollary immediately (Intrinsic Complexity
needs nothing from §3.2 or §3.3); Duality produces its corollary
immediately (Simultaneous Screening needs nothing but Duality applied
twice). A reader never jumps to a separate "Consequences" subsection to
find out what follows from what.

- **Main theorem:** Feature–Sample Duality,
  `(S^F(p))^*=S^S(p^*)` — the theorem the title is selling.
- **Secondary (structural) theorem:** Decomposition, `S=R∘T` — not the
  destination; a structural characterization that the main theorem's
  proof needs.
- **Corollaries** (both stated as `\begin{corollary}`, not
  `\begin{theorem}`, in the actual `.tex`), each attached where it's
  produced, not grouped: Intrinsic Complexity Reduction (§3.1),
  Simultaneous Screening (§3.3).

This matches the actual current file exactly: `\subsection{Feature and
Sample Screening as Operators}` (definitions + Lasso example + SVM
example + Corollary: Intrinsic Complexity Reduction) →
`\subsection{Decomposition of Screening}` (the structural theorem) →
`\subsection{Duality of Screening}` (the main theorem, immediately
followed, same subsection, by `\begin{corollary}[Simultaneous
screening]`).

---

## Hierarchy of the Whole Paper

```
TITLE
Toward a Duality Theory for Feature and Sample Screening
│
├── Central Narrative
│      Feature/Sample screening are Fenchel-dual manifestations
│      of the same structure.
│
├── Section 1 — Introduction
│      Role: pose the question
│
├── Section 2 — Fenchel–Rockafellar Representations and Their
│      Transformations
│      Role: construct the mathematical universe (not screening)
│      Laws: Fenchel Equivariance (translation), Commutativity
│      (restriction)
│
└── Section 3 — Duality Theory
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

| Tier | Result | Section | Attaches to | `.tex` status |
|---|---|---|---|---|
| Main result of the paper | Feature–Sample Duality | 3.3 | — | `\begin{theorem}` |
| Main theorem of the framework | Fenchel Equivariance | 2 | — | `\begin{theorem}` |
| Structural theorem | Decomposition | 3.2 | — | `\begin{theorem}` |
| Corollary | Intrinsic Complexity Reduction | 3.1 | Definitions, same subsection | `\begin{corollary}` |
| Corollary | Simultaneous Screening | 3.3 | Duality, same subsection | `\begin{corollary}` |

("Attaches to" is why there is no separate row/tier for "Consequences"
as a group — each corollary's row already says exactly where it lives.)

No "Theorem 1/2/3" numbering anymore — retired in favor of naming
results by role. This resolves the drift noted in the previous version
of this file (Simultaneous Screening was a numbered `Theorem 3` in
earlier drafts; the author demoted it to a corollary on 2026-07-04,
and this file's hierarchy now reflects that as final).

---

## doc2-universe.tex — narrative recap

(Renamed from `doc2-group.tex`; restructured 2026-07-05 into exactly
the 3 locked subsections — confirmed against the actual file.)

Constructs the mathematical universe screening will later be defined
in: FR representations, translation, restriction, and their two
structural laws — Fenchel Equivariance and Commutativity — that
Section 3 needs. Flow: **§2.1 Fenchel–Rockafellar Representations**
(closed/proper/convex regularity; problem size; separable
representation; "Insight: a closed universe, not just a notation"
paragraph justifying `a`) → **§2.2 Translation of FR Representations**
(Primitive translations merged into one Definition environment;
Translation action `T_k`; Fenchel dual `p^*=(g^*,f^*,-A^T,-a)`;
Involution `(p^*)^*=p` with proof; dual translation `k^*=(-d,-c,-b)`;
Fenchel Equivariance theorem, full proof) → **§2.3 Restriction of FR
Representations** (`R^F_I`,`R^S_J`; Commutativity and Restriction
compatible with translation, both kept without proof by author
instruction, currently unused by any theorem; the two lemmas Section 3
needs) → locked closing paragraph (no separate Summary subsection).

**Correction history worth remembering:** the dual convention and `k^*`
were each flipped twice, in opposite directions, before landing on the
current, verified pair. The file's own `\noteLE` on the Dual
translation definition tells that story in full — read it first if the
signs ever look surprising again.

## doc3-screening.tex — narrative recap

Defines feature and sample screening from optimization assumptions (not
from the translation/restriction formula), illustrates each with a
worked example (Lasso for feature screening, soft-margin SVM for
sample screening — both use the "certificate = 0" special case, where
the translation becomes the identity), states Intrinsic Complexity
Reduction immediately from the definitions, then *discovers* — as
theorems, not definitions — that both screening operators decompose
into Section 2's primitives (Decomposition) and are Fenchel-dual
(Duality, the main result), with Simultaneous Screening falling out as
a two-line corollary of Duality applied twice.

**Section count as of 2026-07-04: 2 theorems (Decomposition, Duality) +
2 corollaries (Intrinsic Complexity Reduction, Simultaneous
Screening).** This matches the Result Tiers table above.

## doc1-intro.tex — narrative recap

Revised 2026-07-05 in three passes, all reflected in the current file
(see the Section 1 entry above for the full flow and the
three-sentence test):

1. **Screening/ML-first reorder:** lead with screening/ML rather than
   Fenchel calculus. Old standalone "FR Model," "Feature Screening,"
   "Sample Screening" subsections folded into "Our Approach: A
   Representation Framework," placed after "Main Insight" and "Why Is
   This Difficult?" instead of previewed earlier.
2. **Historical-accuracy pass:** Background split into "Screening in
   machine learning" and "Historical development" paragraphs; the Gap
   reworded to "model-specific... case-by-case basis, no common
   mathematical language" (not "different mathematical objects"); Main
   Question reworded to "Is there a common mathematical framework that
   explains these seemingly different formulations?"; a new
   "Connection to dual certificates" paragraph added using
   non-reinterpretation phrasing (see `style.md`'s Citing Prior Work
   rules); signature positioning sentence added to Main emphasis.
3. **Full prose pass:** the entire file rewritten as finished academic
   prose, and every `\subsection` removed — one continuous sequence of
   paragraphs under a single `\section{Introduction}`. The boxed Main
   Question and boxed Main Theorem became a plain `quote` block and an
   unboxed `\[ \]` display, respectively (2026-07-04 Formatting Rules,
   applied here for the first time). The "we suppress screening
   parameters" aside moved into a `\footnote`. The three previously
   commented-out citation keys went live:
   `elghaoui2010safe`, `ogawa2014sample`, `shibagaki2016simultaneous`,
   `ndiaye2017gap`, `yamada2021dynamic`, `tran2025one`.

Order (logical, not literal headers): Background (two paragraphs) → The
Gap (question as a plain quote block, no "three gaps," no FR formalism
yet) → Main Insight (the sentence to remember, stated before any
framework) → Why Is This Difficult? (short, no formulas) → Our Approach
(FR model, both screening formulas, dual-certificate connection,
Decomposition, all folded in here instead of previewed earlier) → Main
Theorem → Why Does It Matter? (consequences named, not detailed) →
Main Contributions (3, tiered, as prose not `\paragraph` labels) →
Organization (also prose, not an `itemize`).

Organization paragraph still says the simultaneous-screening corollary
is stated "immediately" after Duality, matching the no-Consequences-
subsection structure of doc3 — no stale "(Theorem~3)" label.

## Known inconsistency outside doc1/doc2/doc3 (flagging only)

`meta/data.tex`'s `\paperAbstract` still claims "we further show that
the two screening operators commute" — this is the exact claim that
was found false and replaced by Simultaneous Screening. Not fixed in
this pass (out of scope: paper.md/narrative.md only); logged in
paper.md's TODO as a real factual error in reader-facing text, not
merely a stale label.
