# Paper Content

This file stores **what the paper contains**. It evolves with the
draft. Process rules live in `agent.md`; style rules live in
`style.md`. Synced 2026-07-05 against the current `doc1-intro.tex`,
`doc2-universe.tex`, `doc3-screening.tex`, and `meta/data.tex` (source
of truth for logic, narrative, and results); historical narrative from
earlier revisions has been trimmed since git now tracks it.

## Flagged for the Author

Confirmed by the author on 2026-07-05, recorded here so future syncs
don't silently re-litigate them:

1. **The Positioning Sentence device is intentionally gone.** Earlier
   drafts had one sentence, right after the Main Question, stating
   *"The goal of this paper is not to argue that feature screening and
   sample screening are dual. Rather, it is to formulate this apparent
   duality..."* The current `doc1-intro.tex` no longer has this
   sentence anywhere, and the author confirmed this is final: the
   two-question framing plus the "Central idea" paragraph now do that
   job implicitly. Do not reintroduce it.
2. **One question became two, confirmed final.** The boxed question is
   *"Can feature screening and sample screening be formulated as
   mathematical transformations independent of specific optimization
   models? If so, in what mathematical sense are they dual?"* Q1
   (existence of a model-independent formulation) is answered
   implicitly across "Central idea" / "Class of problems" / "Class of
   objects"; Q2 (the duality sense) is answered explicitly in "Answer
   to Q2." This is locked, not a draft slip.
3. **doc3's stale cross-reference is fixed.** The closing remark of
   "Decomposition of Screening" previously said results "follow from
   Section~\ref{sec:operators}'s Translation Duality alone"; it now
   correctly credits both Translation Duality and Restriction Duality,
   matching `thm:duality`'s actual proof (fixed 2026-07-05, text-only
   change, no math/logic touched).

Still open, informational only (not blocking): "Why Is This
Difficult?" and "Why Does It Matter?" are no longer separate, named
beats in Section 1; their content is folded into "Structural insight"
and "Answer to Q2" / "Contributions" respectively. Documented below as
the current, compressed structure.

## Title

**Toward a Duality Theory for Feature and Sample Screening** — already
set in `meta/data.tex`. The title promises exactly one thing: a duality
theory. It does not promise a framework, a group action, or a calculus
— those are means, not what the paper is titled after.

## Central Narrative

One sentence. Everything else in the paper exists to set it up, prove
it, or draw consequences from it, no competing narrative:

> Screening is equivariant under Fenchel–Rockafellar duality: feature
> screening and sample screening are the same transformation, read on
> a primal and on its dual FR representation.

This is the abstract's own framing (`meta/data.tex`), now also the
draft's preferred vocabulary throughout Section 1 ("equivariant"
appears directly in the "Structural insight" and "Answer to Q2"
paragraphs). It is equivalent to, and now preferred over, the older
phrasing "this paper gives a mathematical formulation of the apparent
duality between feature screening and sample screening" — keep both in
mind when reading older commit history, but use the equivariance
framing going forward.

## Main Question

The boxed question in `doc1-intro.tex` is now two sentences, asked
together:

> Can feature screening and sample screening be formulated as
> mathematical transformations independent of specific optimization
> models? If so, in what mathematical sense are they dual?

Call these **Q1** (existence of a model-independent formulation) and
**Q2** (the sense of duality). Q1 is answered implicitly, not with a
single labeled sentence: the "Central idea," "Class of problems," and
"Class of objects" paragraphs together construct the FR-representation
language and show feature/sample screening act as transformations on
it. Q2 is answered explicitly, labeled `\noteCLAUDE{Answer to Q2.}` in
the source, by the equivariance identity `(S^F(p))^*=S^S(p^*)`.

Preceded by: Context → Classification → Scope → Historical development
→ Tension and gap. The two-question wording is locked (confirmed
2026-07-05); do not collapse back to the single-question wording used
in earlier passes.

## Main Answer

We formulate the apparent duality between feature screening and sample
screening as an equivariance relation between transformations on
Fenchel–Rockafellar representations:
\[
(S^F(p))^* = S^S(p^*).
\]
This is proved, not assumed: both operators are shown to decompose into
the same two primitives (translation, restriction), and the identity
above then follows from two duality laws, **Translation Duality** and
**Restriction Duality**, connecting those primitives to
Fenchel–Rockafellar duality.

The paper does not introduce a new screening rule. Its contribution is
a structural *duality theory*, not a structural *framework* for its own
sake. This does not compete with prior screening rules (Ghaoui, Ogawa,
Shibagaki, etc.); it operates one level up, extracting common structure
from derivations that were each built model-by-model.

## Main Theorem Presentation

The commutative diagram is the right way to make the paper's novelty
visible, but it must not open the presentation. The locked order:
transition in words, give the formula, give a plain-language
restatement, then give the diagram, last, as interpretation.

1. Transition: state that the identity below is the answer to Q2.
2. Formula (the anchor):
   \[
   (S^F(p))^*=S^S(p^*).
   \]
3. Plain-language restatement: feature screening on a primal
   representation is exactly sample screening on its dual
   representation.
4. Diagram, last, as interpretation:
   \[
   \begin{array}{ccc}
   p & \xrightarrow{S^F} & S^F(p)\\
   {\scriptstyle *}\big\downarrow & & \big\downarrow{\scriptstyle *}\\
   p^* & \xrightarrow{S^S} & S^S(p^*)
   \end{array}
   \]

Applied in both `doc1-intro.tex`'s "Answer to Q2" paragraph and
`doc3-screening.tex`'s Duality of Screening subsection (Interpretation
paragraph, after `thm:duality`'s proof). Both now carry the diagram;
the earlier TODO asking for doc3's diagram is resolved.

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
   FR Duality    → law: Involution        ((p*)* = p)
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
convex), stated inline rather than as separate labeled lemmas. doc3's
own prose narrating this combination now correctly names both
Translation Duality and Restriction Duality (fixed 2026-07-05).

## Section-Level Roles

- **Section 1 — Introduction** (`doc1-intro.tex`). One continuous
  sequence of paragraphs under a single `\section{Introduction}`, no
  `\subsection` anywhere. Pose the question(s); resolve nothing
  technical until "Class of objects" onward. Current logical flow, in
  order:
  1. **Context** — screening as a general cost-reduction technique in
     large-scale convex optimization.
  2. **Classification** — safe vs. unsafe, static/dynamic/sequential,
     tighter safe regions (ball, dome, ellipsoid), and generalizations
     (squeezing, relaxing, peeling), each cited.
  3. **Scope** — this paper's axis is the screening target (feature
     vs. sample), and its level is the structural theory, not the
     safety conditions.
  4. **Historical development** — feature screening's origin in sparse
     learning (Lasso), sample screening's later origin as a transfer
     of the feature-screening philosophy to the SVM dual, their
     parallel evolution, and existing combined/FR-duality-based
     frameworks.
  5. **Tension and gap** — the relationship is suggestive but never
     formulated mathematically; existing work is model-specific.
  6. **Boxed questions Q1, Q2** — see Main Question above.
  7. **Central idea** — answers Q1 in prose: a common class of
     optimization problems is needed before duality and screening can
     be compared as transformations on the same objects.
  8. **Class of problems** — the FR quadruple's underlying
     optimization problem, the list of models it covers (Lasso,
     Elastic Net, logistic regression, Huber regression, KL
     regression, SVMs), each cited.
  9. **Class of objects** — the quadruple `p=(f,g,A,a)`, the class
     `Γ`, its closure under FR duality; feature and sample screening
     restated as assumptions on `p`, each with its reduced-problem
     formula.
  10. **Structural insight** — screening is not primitive; both
      decompose into translation then restriction, and both primitives
      are equivariant under FR duality (no formula for the
      decomposition itself is displayed, by the author's choice).
  11. **Answer to Q2** — the equivariance identity
      `(S^F(p))^*=S^S(p^*)`, stated as following from the structural
      insight, then the commutative diagram, presented as the
      identity's mathematical formulation, not merely an illustration
      of it.
  12. **Contributions** — two, restated in terms of the research
      question: (i) the common mathematical language (FR
      representations, duality, translation, restriction, all
      equivariant), (ii) the mathematical formulation and proof of the
      duality itself, with intrinsic complexity reduction and
      simultaneous screening as direct consequences, and safe
      screening named as future work.
  13. **Organization** — previews Sections 2 and 3.

  Citations introduced in Context/Classification/Historical
  development: `elghaoui2010`, `tibshirani2012strong`, `fan2018sure`,
  `bonnefoy2014dynamic`, `wang2013lasso`, `tran2022beyond`,
  `dai2012ellipsoid`, `elvira2020safe`, `guyard2022screen`,
  `guyard2023safe`, `elghaoui2010safe`, `ogawa2014sample`,
  `shibagaki2016simultaneous`, `ndiaye2017gap`, `yamada2021dynamic`,
  `tran2025one`; in Class of problems: `wang2014safe`, `chen2020safe`,
  `dantas2021safe`, `zhai2020safe`, `nguyen2026gap`. All keys exist in
  `meta/refs.bib` (checked 2026-07-05).
- **Section 2 — FR Representations and Equivariant Transformations**
  (`doc2-universe.tex`, `\label{sec:operators}`; title now includes
  "Equivariant," matching the section's own framing sentence). Does
  not study screening; constructs the mathematical universe in which
  screening will later be defined. **Four subsections**, one object and
  three transformations, each with a single role and a single law:

  **§2.1 — FR Representations.** *Role:* introduce the object.
  *Content:* the quadruple `p=(f,g,A,a)`, problem size
  `size(p):=(m,n)` (also called intrinsic complexity), separability,
  the classes `Γ_{m,n}` and `Γ`, and the closure remark: this class is
  closed under all three transformations studied in the section
  (duality, translation, restriction) — this, not notational neatness,
  is why the constant `a` exists.

  **§2.2 — FR Duality** (renamed from "Duality"). *Role:* introduce
  the first transformation. *Content:* opens with a plain-prose
  paragraph defining the Fenchel conjugate `h^*` and biconjugation
  `h^{**}=h` for closed/proper/convex `h` (no `\begin{definition}`
  environment, by author's choice), then the FR dual
  `p^*=(g^*,f^*,-A^T,-a)`, the remark that `*: Γ → Γ` is a
  transformation exchanging the roles of `f`/`g` and of domain/slope
  translation. *Law:* **Involution**, `(p*)*=p`
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

**Whole-paper narrative in three roles:** Section 1 asks the question
(now two, Q1 and Q2). Section 2 builds a mathematical universe (one
object, three transformations, three laws). Section 3 defines screening
in that universe and proves the main theorem, answering Q2. No section
overlaps another's job.

## Section 2 Internal Order

Exactly four subsections, matching `doc2-universe.tex`. Object →
Transformations (FR duality, translation, restriction) → each with its
own law.

**§2.1 — FR Representations:**
1. Define `p=(f,g,A,a)`, closed/proper/convex `f,g`, separable;
   problem size `size(p):=(m,n)`; the classes `Γ_{m,n}`, `Γ`.
2. State the closure property: this class is closed under duality,
   translation, and restriction — why `a` exists.

**§2.2 — FR Duality** (law: Involution):
3. Plain-prose Fenchel conjugate paragraph (`h^*`, biconjugation),
   ahead of the FR dual formula.
4. Define `p^*=(g^*,f^*,-A^T,-a)`; note `*:Γ→Γ` exchanges `f`/`g` and
   domain/slope translation.
5. **Law: Involution.** `(p^*)^*=p`, full proof.

**§2.3 — Translation** (law: Translation Duality):
6. Define the three primitive translations `T^d,T^v,T^s`; package into
   `T_k` together with the dual parameter `k^*=(-d,-c,-b)` (one merged
   Definition).
7. State the Abelian translation-action fact (kept informal, not a
   proposition, by author choice) and the three-part conjugate
   identity for primitive translations.
8. **Law: Translation Duality.** `(T_k(p))^*=T_{k^*}(p^*)`, full proof.

**§2.4 — Restriction** (law: Restriction Duality):
9. Define index notation (`x_I,g_I,A_I,A_J,A_{J,I}`) and feature/sample
   restriction `R^F_I,R^S_J`, with explicit domain/codomain typing.
10. **Law: Restriction Duality.** `(R^F_I(p))^*=R^S_I(p^*)`
    (symmetrically), full proof.

| Piece | Gives |
|---|---|
| Representation | a closed universe |
| FR Duality | a transformation; law: Involution |
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
   Closing remark now correctly credits both Translation Duality and
   Restriction Duality (fixed 2026-07-05).

**§3.3 — Duality of Screening:**
6. **Main theorem.** `(S^F_{I,z}(p))^* = S^S_{I,z}(p^*)`, symmetrically.
   Proof combines Decomposition with Translation Duality and
   Restriction Duality (doc2) as three explicit steps, plus two
   convex-analysis facts (conjugate of a separable restriction;
   sub-block regularity) stated inline. Feature and sample screening
   are not shown to commute on the same `p`; they don't need to, since
   they are Fenchel-dual images of each other. Interpretation paragraph
   now carries the commutative diagram.
7. **Corollary: Simultaneous Screening** — attaches here, immediately
   after Duality, same subsection: needs Duality applied twice and
   Involution, nothing else. Replaces the earlier, incorrect
   Commutativity claim.

## Section Roadmap

| Section | Role | Purpose |
|---|---|---|
| 1. Introduction | Pose Q1 and Q2 | Context, classification, and scope of screening; historical development; the gap; the two boxed questions; the central idea and FR-representation language answering Q1; screening restated in that language; the structural insight (decomposition + primitive equivariance); the equivariance identity answering Q2; contributions; organization. |
| 2. FR Representations and Equivariant Transformations | Build the universe screening will live in — Object → three Transformations → three Laws | §2.1 the FR representation, closed under duality/translation/restriction; §2.2 FR duality and its law, Involution; §2.3 translation and its law, Translation Duality; §2.4 restriction and its law, Restriction Duality. Does not define screening or answer Q1/Q2. |
| 3. Duality of Feature and Sample Screening | Score the paper's points, answer Q2 in full technical detail | §3.1 define `S^F,S^S` semantically, immediately state Intrinsic Complexity Reduction; §3.2 prove Decomposition; §3.3 prove Duality, immediately state Simultaneous Screening. No "Consequences" subsection. |

## Dependency Graph (paper-level)

FR representation `p=(f,g,A,a) ∈ Γ_{m,n}` [Section 2 object, closed
under all three transformations below]
     │
     ├─→ FR Duality (`p ↦ p*`) → **Involution** (`(p*)*=p`)
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
               Translation Duality, and Restriction Duality; answers Q2]
               │
               └─→ **Simultaneous Screening** [corollary — needs
                    Duality applied twice and Involution; doc3 §3.3,
                    same subsection]

Both Translation Duality and Restriction Duality feed forward directly
into the main theorem's proof — neither is a narrated-for-symmetry
leaf. Involution feeds forward into Simultaneous Screening.

## Fixed Notation

FR representation and its transformations:

- FR representation: `p=(f,g,A,a)` — closed, proper, convex `f,g`,
  separable; represents `p(x)=f(Ax)+g(x)+a`.
- Problem size / intrinsic complexity: `size(p):=(m,n)`.
- `Γ_{m,n}`: the set of FR representations of size `(m,n)`. `Γ`: the
  set of FR representations of any size.
- Fenchel conjugate: `h^*(y):=sup_x{⟨y,x⟩−h(x)}`; `h^{**}=h` when `h`
  is closed, proper, convex (doc2's plain-prose paragraph, §2.2).
- **FR Duality: `p^* = (g^*, f^*, -A^T, -a)`** (constant negated),
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

## Fixed Terminology

See `style.md` → "Fenchel / FR Terminology" for the locked distinction
between FR representation, FR duality, Fenchel conjugate, and
Fenchel--Young equality, and the rule that "Fenchel--Rockafellar" is
spelled out in full exactly twice in the whole paper (abstract, and the
introduction's first use), abbreviated "FR" everywhere else.

- FR representation, FR duality (involution).
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
derivation trail if the signs ever need re-checking. Narrative-level
open items (not mathematical) are listed under "Flagged for the
Author" above.

## TODO

- **doc2 and doc3 both spell out "Fenchel--Rockafellar" in full,
  repeatedly, outside the abstract/intro.** Under the newly locked
  Fenchel/FR terminology rule (`style.md`), every occurrence past the
  introduction's first use should read "FR" instead. Known instances:
  doc2's Motivation paragraph and `[FR representation]`/`[FR Duality]`
  definitions ("A Fenchel--Rockafellar representation is...", "The
  Fenchel--Rockafellar dual of..."), Translation's Interpretation
  paragraph, and the section's own opening paragraph; doc3's opening
  paragraph, the SVM example ("represented in Fenchel--Rockafellar
  form"), and the Duality of Screening subsection's opening paragraph.
  Not yet swept — flagged for the author before editing doc2/doc3
  directly.

- ~~doc3 notation conflict (`mathcal{FR}^{sep}_{m,n}` vs. `Γ_{m,n}`)~~
  — **done.** Confirmed swept everywhere in the current doc3.
- ~~doc3's Duality theorem has no commutative diagram~~ — **done.**
  Present in the Interpretation paragraph after `thm:duality`'s proof.
- ~~`meta/data.tex`'s `\paperAbstract` claims the two screening
  operators commute~~ — **done.** Current abstract instead says
  screening is equivariant under FR duality and does not use the word
  "commute."
- ~~doc3's Decomposition-subsection closing remark credited
  "Translation Duality alone"~~ — **done.** Now credits both
  Translation Duality and Restriction Duality.
- ~~Positioning Sentence device removal~~ — **confirmed final by the
  author, 2026-07-05.** Do not reintroduce it.
- ~~Single vs. two Main Question wording~~ — **confirmed final by the
  author, 2026-07-05.** The two-question (Q1, Q2) wording is locked.
- Minor rigor gap, not a correctness issue: `doc2-universe.tex` and
  `doc3-screening.tex` state `(g_I)^*=(g^*)_I` and sub-block
  regularity as "basic convex-analysis facts" without a citation; the
  author intends to add one before submission (see doc3's `\noteLE` at
  that step).
