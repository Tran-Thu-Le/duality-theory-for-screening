# Paper Content

This file stores **what the paper contains**. It evolves with the
draft. Process rules live in `agent.md`; style rules live in
`style.md`. Synced 2026-07-05 against the current `doc2-universe.tex`
and `doc3-screening.tex` (source of truth for logic and results);
historical narrative from earlier revisions has been trimmed since git
now tracks it.

## Title

**Toward a Duality Theory for Feature and Sample Screening** — already
set in `meta/data.tex`. The title promises exactly one thing: a duality
theory. It does not promise a framework, a group action, or a calculus
— those are means, not what the paper is titled after.

## Central Narrative

One sentence. Everything else in the paper exists to set it up, prove
it, or draw consequences from it, no competing narrative:

> This paper gives a mathematical formulation of the apparent duality
> between feature screening and sample screening.

This names the contribution (formalizing) rather than the conclusion
(that they are dual), which is what the Main Theorem proves, not what
the paper claims about itself up front. The framework (translation,
restriction, duality, and their three laws) is not itself a
destination; it exists only to make this one sentence provable.

## Main Question

> However, this similarity has remained informal. Although the two
> paradigms appear to be dual, it remains unclear in what mathematical
> sense this duality should be understood.
>
> **Is there a common mathematical framework that explains these
> seemingly different, model-specific formulations?**

(`doc1-intro.tex`'s exact wording may differ slightly in the boxed
question itself; the historical lead-in above is locked and precedes
it. See doc1 for the author's current in-file phrasing.)

Followed directly by the Positioning Sentence, then Main Answer.

## Positioning Sentence

Immediately after the Main Question, before any technical content, the
paper states what its contribution is not, and what it is:

> The goal of this paper is not to argue that feature screening and
> sample screening are dual. Rather, it is to formulate this apparent
> duality as a precise mathematical statement.

This pre-empts the objection "this duality was already informally
known" by naming *formalization*, not discovery, as the contribution.
It appears exactly once, right after the Main Question; Main Insight
and the Main Theorem's presentation do not repeat it.

Locked flow for Section 1: Main Question → Positioning Sentence → Main
Insight → Why Is This Difficult? → Our Approach → Main Theorem → Why
Does It Matter? → Contributions → Organization.

## Main Answer

We formulate the apparent duality between feature screening and sample
screening as a commutative relation between transformations on
Fenchel–Rockafellar representations:
\[
(S^F(p))^* = S^S(p^*).
\]
This is proved, not assumed: both operators are shown to decompose into
the same two primitives (translation, restriction), and the
commutative relation above then follows from two duality laws,
**Translation Duality** and **Restriction Duality**, connecting those
primitives to Fenchel–Rockafellar duality.

The paper does not introduce a new screening rule. Its contribution is
a structural *duality theory*, not a structural *framework* for its
own sake. Signature positioning sentence (doc1's "Main emphasis"
paragraph): *"Existing screening methods are typically derived in a
model-specific manner; our goal is not to derive another screening
rule, but to identify the common mathematical structure underlying
these derivations."* This does not compete with prior screening rules
(Ghaoui, Ogawa, Shibagaki, etc.); it operates one level up, extracting
common structure from derivations that were each built model-by-model.

## Main Theorem Presentation

The commutative diagram is the right way to make the paper's novelty
visible, but it must not open the presentation. The locked order:
transition in words (without re-arguing novelty, already said once, in
the Positioning Sentence), give the formula, give a plain-language
restatement, then give the diagram, last, as interpretation.

1. Transition: *"The formulation promised above is the following
   identity."*
2. Formula (the anchor):
   \[
   (S^F(p))^*=S^S(p^*).
   \]
3. Plain-language restatement: *"Equivalently, dualizing after feature
   screening gives the same representation as applying sample
   screening after dualizing."*
4. Diagram, last, as interpretation:
   \[
   \begin{array}{ccc}
   p & \xrightarrow{S^F} & S^F(p)\\
   {\scriptstyle *}\big\downarrow & & \big\downarrow{\scriptstyle *}\\
   p^* & \xrightarrow{S^S} & S^S(p^*)
   \end{array}
   \]

Applied in `doc1-intro.tex`'s Main Theorem paragraph. **Still open:**
doc3's `\begin{theorem}[Dual of screening]` states the identity and an
Interpretation paragraph but has no diagram; adding it there is a
reasonable next step, not yet done.

## Result Hierarchy

The authoritative ranking of every proved result, by narrative weight.
Nothing below should be described in prose as co-equal to the tier
above it.

1. **Main result of the paper — Feature–Sample Duality** (doc3,
   subsection "Duality of Screening", `thm:duality`):
   \[
   (S^F(p))^* = S^S(p^*).
   \]
   This is the theorem the title sells.
2. **Framework laws — one per transformation** (doc2). Duality is
   treated as a third transformation, alongside translation and
   restriction, each closing the class of FR representations and each
   carrying exactly one structural law:
   ```
   Duality       → law: Involution        ((p*)* = p)
   Translation   → law: Translation Duality  ((T_k(p))* = T_{k*}(p*))
   Restriction   → law: Restriction Duality  ((R^F_I(p))* = R^S_I(p*), symmetrically)
   ```
   - **Involution** (`prop:involution`): duality's own law, proved.
   - **Translation Duality** (`thm:fenchel-equivariance` label,
     proposition named "Translation Duality" in text): translation's
     compatibility with duality, proved, and directly cited by name in
     doc3's Duality theorem.
   - **Restriction Duality** (`prop:restriction-equivariance`):
     restriction's compatibility with duality, proved, and directly
     cited by name in doc3's Duality theorem.
   No law is itself the paper's contribution; all three are machinery,
   the most important machinery, but still machinery. There is no
   Commutativity result in this paper; an earlier attempt at one was
   dropped (see Open Problems).
3. **Structural theorem — Decomposition** (doc3, subsection
   "Decomposition of Screening", `thm:decomposition`):
   \[
   S^F=R^F\circ T^F,
   \qquad
   S^S=R^S\circ T^S.
   \]
   Not a destination — the structural characterization that the main
   theorem's proof needs, and the fact that makes "Screening =
   Translation + Restriction" a theorem rather than a definition.
4. **Corollaries — attached locally to the result that produces them,
   never grouped into a shared "Consequences" subsection:**
   - **Intrinsic Complexity Reduction** (`cor:complexity`) attaches to
     §3.1 (Definitions) — needs only the two definitions, nothing from
     tiers 2 or 3, so it is stated before Decomposition even exists.
     Re-derived (for free, a remark) once Decomposition is available.
   - **Simultaneous Screening** (`cor:simultaneous`) attaches to §3.3
     (Duality) — needs Duality applied twice and the Involution law,
     nothing else, so it is stated in the same subsection as Duality,
     immediately after it. This is the replacement for a Commutativity
     claim that turned out to be false in general.

The proof of the main theorem now combines three named results as
explicit steps: Decomposition (tier 3), Translation Duality, and
Restriction Duality (tier 2) — plus two basic convex-analysis facts
(conjugate of a separable restriction; a finite sum of closed, proper,
convex functions restricted to a sub-block is itself closed, proper,
convex), stated inline rather than as separate labeled lemmas.

## Section-Level Roles

- **Section 1 — Introduction** (`doc1-intro.tex`). One continuous
  sequence of paragraphs under a single `\section{Introduction}`, no
  `\subsection` anywhere. Pose the question; resolve nothing technical.
  Logical flow: Background (screening in ML, historical development,
  citations: `elghaoui2010safe`, `ogawa2014sample`,
  `shibagaki2016simultaneous`, `ndiaye2017gap`, `yamada2021dynamic`,
  `tran2025one`) → the Gap → Main Question → Positioning Sentence →
  Main Insight → Why Is This Difficult? → Our Approach (framework as
  proof strategy; FR model, the two screening formulas, dual-certificate
  interpretation) → Main Theorem → Why Does It Matter? → Main
  Contributions → Organization. Three-sentence test anchors the whole
  section (doc1's opening paragraph).
- **Section 2 — FR Representations and Transformations**
  (`doc2-universe.tex`, `\label{sec:operators}`). Does not study
  screening; constructs the mathematical universe in which screening
  will later be defined. **Four subsections**, one object and three
  transformations, each with a single role and a single law:

  **§2.1 — FR Representations.** *Role:* introduce the object.
  *Content:* the quadruple `p=(f,g,A,a)`, problem size
  `size(p):=(m,n)` (also called intrinsic complexity), separability,
  the classes `Γ_{m,n}` and `Γ`, and the closure remark: this class is
  closed under all three transformations studied in the section
  (duality, translation, restriction) — this, not notational neatness,
  is why the constant `a` exists.

  **§2.2 — Duality.** *Role:* introduce the first transformation.
  *Content:* the FR dual `p^*=(g^*,f^*,-A^T,-a)`, the remark that
  `*: Γ → Γ` is a transformation exchanging the roles of `f`/`g` and of
  domain/slope translation. *Law:* **Involution**, `(p*)*=p`
  (`prop:involution`, proved) — duality's own structural law.

  **§2.3 — Translation.** *Role:* introduce the second transformation.
  *Content:* the three primitive translations (`T^d`, `T^v`, `T^s`, one
  merged Definition), then one merged Definition for the translation
  `T_k` and its dual parameter `k^*=(-d,-c,-b)` (spaces `K`, `K^*`); the
  Abelian translation-action fact, kept as informal prose by author
  choice, not promoted to a proposition; the three-part conjugate
  identity for primitive translations (`prop:duality-of-primitive-
  translations`). *Law:* **Translation Duality**
  (`thm:fenchel-equivariance` label), `(T_k(p))^*=T_{k^*}(p^*)`, proved,
  cited by name in doc3's Duality theorem.

  **§2.4 — Restriction.** *Role:* introduce the third transformation.
  *Content:* index notation (`x_I`, `g_I`, `A_I`, `A_J`, `A_{J,I}`), one
  merged Definition for feature restriction `R^F_I:Γ_{m,n}→Γ_{m,|I|}`
  and sample restriction `R^S_J:Γ_{m,n}→Γ_{|J|,n}`. *Law:* **Restriction
  Duality** (`prop:restriction-equivariance`),
  `(R^F_I(p))^*=R^S_I(p^*)` (symmetrically), proved, cited by name in
  doc3's Duality theorem.

  Doc2 no longer has a separate closing/Summary subsection; it ends
  with Restriction Duality's usage note. There is no Commutativity
  result anywhere in the section (see Open Problems for why it was
  dropped).

  Transition to Section 3: a reader who has just been given Object →
  Three Transformations → Three Laws naturally asks where screening
  fits. Section 3 opens by answering: screening is **not** a primitive
  transformation, it is a **derived** transformation obtained by
  combining translation and restriction.
- **Section 3 — Duality of Feature and Sample Screening**
  (`doc3-screening.tex`, `\label{sec:screening}`). This is where the
  paper scores its points. No "Consequences" subsection; each corollary
  is narrated immediately after the result that produces it:
  ```
  3.1 Feature and Sample Screening as Operators (S^F, S^S)
      → Corollary: Intrinsic Complexity Reduction

  3.2 Decomposition of Screening (structural theorem)

  3.3 Duality of Screening (main theorem)
      → Corollary: Simultaneous Screening
  ```
  Doc3's own opening paragraph frames this as two main results
  (Decomposition, Duality) plus, as a by-product, intrinsic complexity
  reduction and simultaneous screening — consistent with this tiering.

**Whole-paper narrative in three roles:** Section 1 asks a question.
Section 2 builds a mathematical universe (one object, three
transformations, three laws). Section 3 defines screening in that
universe and proves the main theorem. No section overlaps another's
job.

## Section 2 Internal Order

Exactly four subsections, matching `doc2-universe.tex`. Object →
Transformations (duality, translation, restriction) → each with its own
law.

**§2.1 — FR Representations:**
1. Define `p=(f,g,A,a)`, closed/proper/convex `f,g`, separable;
   problem size `size(p):=(m,n)`; the classes `Γ_{m,n}`, `Γ`.
2. State the closure property: this class is closed under duality,
   translation, and restriction — why `a` exists.

**§2.2 — Duality** (law: Involution):
3. Define `p^*=(g^*,f^*,-A^T,-a)`; note `*:Γ→Γ` exchanges `f`/`g` and
   domain/slope translation.
4. **Law: Involution.** `(p^*)^*=p`, full proof.

**§2.3 — Translation** (law: Translation Duality):
5. Define the three primitive translations `T^d,T^v,T^s`; package into
   `T_k` together with the dual parameter `k^*=(-d,-c,-b)` (one merged
   Definition).
6. State the Abelian translation-action fact (kept informal, not a
   proposition, by author choice) and the three-part conjugate
   identity for primitive translations.
7. **Law: Translation Duality.** `(T_k(p))^*=T_{k^*}(p^*)`, full proof.

**§2.4 — Restriction** (law: Restriction Duality):
8. Define index notation (`x_I,g_I,A_I,A_J,A_{J,I}`) and feature/sample
   restriction `R^F_I,R^S_J`, with explicit domain/codomain typing.
9. **Law: Restriction Duality.** `(R^F_I(p))^*=R^S_I(p^*)`
   (symmetrically), full proof.

| Piece | Gives |
|---|---|
| Representation | a closed universe |
| Duality | a transformation; law: Involution |
| Translation | a transformation; law: Translation Duality |
| Restriction | a transformation; law: Restriction Duality |

## Section 3 Internal Order

No "Consequences" subsection: each corollary is narrated immediately
after the result that produces it.

**§3.1 — Feature and Sample Screening as Operators:**
1. Motivate from the optimization objective `p(x)=f(Ax)+g(x)+a`.
2. **Feature screening**, from the assumption `x_Ī=z`:
   `S^F_{I,z}(p) = (T^d_{A_Ī z}f, g_I, A_I, a+g_Ī(z))`. Illustrated by
   the Lasso example (`z=0` recovers classical Lasso feature
   screening).
3. **Sample screening**, from the assumption `s∈∂f_J̄(A_J̄x)`, via
   Fenchel–Young equality: `S^S_{J,s}(p) = (f_J, T^s_{A_J̄^T s}g, A_J,
   a-f_J̄^*(s))`. Illustrated by the soft-margin SVM example (`s=0`
   recovers classical SVM sample screening; footnote to `ogawa2013` for
   the general subgradient case).
4. **Corollary: Intrinsic Complexity Reduction** — attaches here, needs
   only the two definitions above.

**§3.2 — Decomposition of Screening:**
5. **Structural theorem.** `S^F=R^F∘T^F`, `S^S=R^S∘T^S`, proved from
   the translation and restriction definitions alone (no proposition or
   lemma needed). Re-derives step 4's corollary for free, as a remark.

**§3.3 — Duality of Screening:**
6. **Main theorem.** `(S^F_{I,z}(p))^* = S^S_{I,z}(p^*)`, symmetrically.
   Proof combines Decomposition with Translation Duality and
   Restriction Duality (doc2) as three explicit steps, plus two
   convex-analysis facts (conjugate of a separable restriction;
   sub-block regularity) stated inline. Feature and sample screening
   are not shown to commute on the same `p`; they don't need to, since
   they are Fenchel-dual images of each other.
7. **Corollary: Simultaneous Screening** — attaches here, immediately
   after Duality, same subsection: needs Duality applied twice and
   Involution, nothing else. Replaces the earlier, incorrect
   Commutativity claim.

## Section Roadmap

| Section | Role | Purpose |
|---|---|---|
| 1. Introduction | Pose the question | Lead with screening/ML; state Main Insight before any framework; explain the obstacle; introduce the framework as proof strategy; preview the main theorem without proving it; state consequences without detailing them. |
| 2. FR Representations and Transformations | Build the universe screening will live in — Object → three Transformations → three Laws | §2.1 the FR representation, closed under duality/translation/restriction; §2.2 duality and its law, Involution; §2.3 translation and its law, Translation Duality; §2.4 restriction and its law, Restriction Duality. Does not define screening or answer the main question. |
| 3. Duality of Feature and Sample Screening | Score the paper's points | §3.1 define `S^F,S^S` semantically, immediately state Intrinsic Complexity Reduction; §3.2 prove Decomposition; §3.3 prove Duality, immediately state Simultaneous Screening. No "Consequences" subsection. |

## Dependency Graph (paper-level)

FR representation `p=(f,g,A,a) ∈ Γ_{m,n}` [Section 2 object, closed
under all three transformations below]
     │
     ├─→ Duality (`p ↦ p*`) → **Involution** (`(p*)*=p`)
     │
     ├─→ Translation (`T^d,T^v,T^s` → `T_k`, dual parameter `k*`)
     │    → **Translation Duality** (`(T_k(p))*=T_{k*}(p*)`)
     │
     └─→ Restriction (`R^F_I`, `R^S_J`)
          → **Restriction Duality** (`(R^F_I(p))*=R^S_I(p*)`,
            symmetrically)

→ Feature screening / Sample screening, defined semantically (doc3
§3.1)
     │
     ├─→ **Intrinsic Complexity Reduction** [corollary — needs only
     │    the definitions above; doc3 §3.1]
     │
     └─→ **Decomposition** (`S^F=R^F∘T^F`, `S^S=R^S∘T^S`)
          [structural theorem; doc3 §3.2]
          │
          └─→ **Feature–Sample Duality** (`(S^F(p))^*=S^S(p^*)`)
               [main result; doc3 §3.3 — proof combines Decomposition,
               Translation Duality, and Restriction Duality]
               │
               └─→ **Simultaneous Screening** [corollary — needs
                    Duality applied twice and Involution; doc3 §3.3,
                    same subsection]

Unlike earlier drafts, both Translation Duality and Restriction Duality
now feed forward directly into the main theorem's proof — neither is a
narrated-for-symmetry leaf. Involution feeds forward into Simultaneous
Screening.

## Fixed Notation

FR representation and its transformations:

- FR representation: `p=(f,g,A,a)` — closed, proper, convex `f,g`,
  separable; represents `p(x)=f(Ax)+g(x)+a`.
- Problem size / intrinsic complexity: `size(p):=(m,n)`.
- `Γ_{m,n}`: the set of FR representations of size `(m,n)`. `Γ`: the
  set of FR representations of any size.
- **Duality: `p^* = (g^*, f^*, -A^T, -a)`** (constant negated),
  representing `p^*(y)=g^*(-A^Ty)+f^*(y)-a`. **Involution:**
  `(p^*)^*=p`, proved.

Primitive translations (unified `T` family):

- `T^d_b h := h(·+b)`, `b∈R^m` — domain translation.
- `T^v_c h := h+c`, `c∈R` — value translation.
- `T^s_d h := h+⟨d,·⟩`, `d∈R^n` — slope translation.
  **Case-sensitive pair, by design:** `T^s` (slope) vs. `T^S` (sample
  screening family) — visually close, worth a gut-check on a compiled
  page.

Translation (one merged Definition in doc2: parameter, dual parameter,
and action together):

- Translation parameter: `k=(b,c,d) ∈ K = R^m×R×R^n`.
- Translation action: `T_k : Γ → Γ`, `T_k(p) = (T^d_b f, T^s_d g, A,
  a+c)`.
- Dual translation parameter: `k^* = (-d, -c, -b) ∈ K^* = R^n×R×R^m`.
  `*: K → K^*` satisfies `(k^*)^*=k`.
- Feature translation: `T^F_{I,z} := T_{k^F_{I,z}}`, where
  `k^F_{I,z} := (A_Ī z, g_Ī(z), 0)`.
- Sample translation: `T^S_{J,s} := T_{k^S_{J,s}}`, where
  `k^S_{J,s} := (0, -f_J̄^*(s), A_J̄^T s)`.

Restriction and screening:

- Index notation: for `I⊆{1,...,n}`, `J⊆{1,...,m}`, separable
  `g=Σg_i`, `f=Σf_j`: `x_I:=(x_i)_{i∈I}`, `g_I(x_I):=Σ_{i∈I}g_i(x_i)`,
  `f_J` symmetrically. `A_I:=A_{:,I}` (columns), `A_J:=A_{J,:}` (rows),
  `A_{J,I}:=(A_J)_I=(A_I)_J`.
- Feature restriction: `R^F_I : Γ_{m,n} → Γ_{m,|I|}`, `R^F_I(f,g,A,a) =
  (f,g_I,A_I,a)`.
- Sample restriction: `R^S_J : Γ_{m,n} → Γ_{|J|,n}`, `R^S_J(f,g,A,a) =
  (f_J,g,A_J,a)`.
- Feature screening: `S^F_{I,z} := R^F_I ∘ T^F_{I,z}`.
- Sample screening: `S^S_{J,s} := R^S_J ∘ T^S_{J,s}`.

**Known open notation conflict (not yet fixed, see TODO):** doc3's
opening paragraph uses `p ∈ Γ_{m,n}` (matching doc2), but
`cor:complexity`, `thm:duality`, and `cor:simultaneous` still write
`p ∈ mathcal{FR}^{sep}_{m,n}`, a symbol that is not defined anywhere in
either doc2 or doc3 anymore. Pick one and sweep the other three
occurrences.

## Fixed Terminology

- FR representation, duality (involution).
- Primitive: domain translation, value translation, slope translation
  (`T^d,T^v,T^s`), translation, feature restriction, sample
  restriction.
- Derived: feature translation, sample translation (`T^F,T^S`),
  feature screening, sample screening (`S^F,S^S`).
- Results, by tier: **Involution, Translation Duality, Restriction
  Duality** (Section 2's three framework laws, one per transformation),
  Decomposition (structural theorem), Feature–Sample Duality (main
  result), Intrinsic Complexity Reduction and Simultaneous Screening
  (corollaries).

Feature-sample commutativity is **not** a property of this paper;
Simultaneous Screening (a corollary, not a theorem) is the correct
replacement: composition on `p` relates to composition on `p^*`, not to
itself.

Do not write "Theorem 1/2/3" anywhere. Refer to results by name
(Translation Duality, Restriction Duality, Decomposition,
Feature–Sample Duality) or by tier (main result / framework law /
structural theorem / corollary).

Banned synonyms and their exceptions: see `style.md` → Things That
Should Never Appear.

## Open Problems

None currently open at the level of mathematical content. Resolved:
the sample-screening sign conflict (fixed by negating the FR dual's
constant), and the original Commutativity theorem's cross-term gap
(fixed by dropping that theorem in favor of Simultaneous Screening,
which relates composition on `p` to composition on `p^*` instead of
claiming commutativity on `p` itself). See git history for the
derivation trail if the signs ever need re-checking.

## TODO

- ~~doc3 notation conflict~~ — **done 2026-07-05.** Swept to
  `Γ_{m,n}` everywhere; the undefined `mathcal{FR}^{sep}_{m,n}` symbol
  no longer appears.
- ~~doc3's Duality theorem has no commutative diagram~~ — **done
  2026-07-05.** Added to the Interpretation paragraph, matching doc1's
  Main Theorem presentation.
- ~~doc3 line 4 typo~~ — **done 2026-07-05.** "FR representtaion" →
  "FR representation."
- ~~`\boxed{}` and prose dashes remaining in doc2~~ — **done
  2026-07-05.** Last `\boxed{}` (Translation Duality's statement) and
  the remaining prose dashes in doc2's Motivation paragraphs fixed;
  `Fenchel--Rockafellar`/`Fenchel--Young` en-dash naming is unaffected.
- **`meta/data.tex`'s `\paperAbstract` contradicts the resolved
  finding.** It still says "We further show that the two screening
  operators commute" — false (this is exactly the claim dropped in
  favor of Simultaneous Screening). Needs a full rewrite; also still
  sells the framework more than the locked positioning wants.
- **Section 1 (`doc1-intro.tex`) not re-verified in this pass** — this
  sync prioritized doc2/doc3 per the author's request. Section-Level
  Roles above for Section 1 reflects the last known state; re-check
  doc1 directly before relying on exact wording.
- Minor rigor gap, not a correctness issue: `doc2-universe.tex` states
  `(g_I)^*=(g^*)_I` and `g_Ī` closed/proper/convex as "basic
  convex-analysis facts" without a citation; the author intends to add
  one before submission (see doc3's `\noteLE` at that step).
