# Paper Content

This file stores **what the paper contains**. It evolves with the
draft. Process rules live in `agent.md`; style rules live in
`style.md`.

## Title (locked 2026-07-04)

**Toward a Duality Theory for Feature and Sample Screening** — already
set in `meta/data.tex`. The title promises exactly one thing: a duality
theory. It does not promise a framework, a group action, or a calculus
— those are means, not what the paper is titled after.

## Central Narrative (revised 2026-07-05: contribution-stated, not result-stated)

One sentence. Everything else in the paper exists to set it up, prove
it, or draw consequences from it — no competing narrative:

> This paper gives a mathematical formulation of the apparent duality
> between feature screening and sample screening.

**Why this replaces the earlier wording** (retired: *"Feature screening
and sample screening are not independent techniques but Fenchel-dual
manifestations of the same mathematical structure."*): the old
sentence states a *result* — what the theorem says. A math paper's
central narrative is stronger when it names the *contribution* — the
act of formalizing — rather than the conclusion, because the
conclusion alone invites the reaction "yes, and?" from a reviewer who
already suspects the two are related. "Gives a mathematical
formulation of" names the paper's actual work; the old wording,
"Fenchel-dual manifestations of the same structure," is now what the
Main Theorem proves, not what the paper claims about itself up front.
See the Positioning Sentence and Main Answer below, both revised the
same day for the same reason.

The framework (translation, restriction, Fenchel Equivariance) is not
itself a destination. It exists only to make this one sentence
provable rather than assumed.

## Main Question

**Locked wording (updated 2026-07-05, second revision — duality-first
framing; applied to `doc1-intro.tex` in the 2026-07-05 third-revision
pass):**

Historical lead-in, placed immediately before the question itself:

> However, this similarity has remained informal. Although the two
> paradigms appear to be dual, it remains unclear in what mathematical
> sense this duality should be understood.

Main Question:

> In what mathematical sense are feature screening and sample
> screening dual to one another?

Followed directly by: "This paper answers this question by..." (leads
into Main Answer below).

**Why this revision, and what it replaces:** the previous wording, "Is
there a common mathematical framework that explains these seemingly
different, model-specific formulations?" (2026-07-05, first revision),
undersold the paper's actual claim. The resemblance between the two
paradigms is not in doubt, both use convex duality, and prior work
(Shibagaki et al.) already places them side by side, so asking merely
"is there a common framework" reads as if the resemblance itself were
still uncertain. The new framing instead says the resemblance has
already been noticed informally, but never made mathematically
precise, which is a sharper, more defensible gap and matches the
paper's actual contribution (a precise, proved sense of duality)
rather than a vaguer unifying "framework." This also finally uses the
word the title promises, *duality*, directly in the question, instead
of holding it back for the Main Insight.

Both the "common mathematical framework" wording and the still-earlier
"What is the mathematical relationship between feature screening and
sample screening?" wording are retired.

## Positioning Sentence (locked 2026-07-05, third revision — supersedes two earlier, scattered treatments; applied to doc1-intro.tex)

Immediately after the Main Question, before any technical content
(before Main Insight, before the framework, before the theorem), the
paper states what its contribution is not, and what it is:

> The goal of this paper is not to argue that feature screening and
> sample screening are dual. Rather, it is to formulate this apparent
> duality as a precise mathematical statement.

This is the sentence that changes a reviewer's mindset: it pre-empts
the objection "this duality was already informally known" by naming
*formalization*, not discovery, as the contribution — before the
reviewer has a chance to form that objection on their own.

**This sentence appears exactly once, here, early, right after the
Main Question — not repeated later.** It supersedes two earlier,
separate treatments of the same "no, but" move that are now retired:

1. The Main Insight reframing from 2026-07-05's second revision
   ("No. The novelty is not the intuition that the two paradigms are
   dual. The novelty is that we formulate this intuition as a precise
   commutative diagram...") — **retired**. Main Insight (Section-Level
   Roles, Section 1, below) reverts to stating the actual technical
   idea, not this positioning move, since the positioning move now has
   its own place, earlier.
2. The opening sentence of Main Theorem Presentation below ("We do not
   claim that the analogy between feature screening and sample
   screening is new...") — **retired, removed from Main Theorem
   Presentation**. Repeating it again right before the formula would
   be redundant now that it has already been said once, here. Main
   Theorem Presentation's steps are renumbered accordingly.

Locked flow for Section 1, in order: Main Question → **Positioning
Sentence** → Main Insight → Why Is This Difficult? → Our Approach →
Main Theorem → Why Does It Matter? → Contributions → Organization.

## Main Answer

We formulate the apparent duality between feature screening and sample
screening as a commutative relation between transformations on
Fenchel–Rockafellar representations:
\[
(S^F(p))^* = S^S(p^*).
\]
This is proved, not assumed: both operators are shown to decompose into
the same two primitives (translation, restriction), and the
commutative relation above then follows from one equivariance property
(Fenchel Equivariance) connecting those primitives to
Fenchel--Rockafellar duality.

**Why this replaces the earlier opening** (retired: *"Feature screening
and sample screening are Fenchel-dual operations."*): a flat assertion
that they "are" dual invites the reviewer's reaction "yes, I know, so
what will you change?" Leading with "we formulate... as a commutative
relation" names the contribution (the act of formulating) before
stating what the formulation says, matching the Central Narrative and
Positioning Sentence above.

The paper does not introduce a new screening rule. Its contribution is
a structural *duality theory*, not a structural *framework* for its
own sake. **Signature positioning sentence (locked 2026-07-05, doc1's
"Main emphasis" paragraph):** *"Existing screening methods are
typically derived in a model-specific manner; our goal is not to
derive another screening rule, but to identify the common mathematical
structure underlying these derivations."* This explicitly does not
compete with prior screening rules (Ghaoui, Ogawa, Shibagaki, etc.) —
it operates one level up, extracting common structure from derivations
that were each built model-by-model.

## Main Theorem Presentation (locked 2026-07-05, revised same day — opening sentence moved to Positioning Sentence above; applied to doc1-intro.tex)

The commutative diagram is the right way to make the paper's novelty
visible, but it must not open the presentation. Leading with a
category-looking diagram reads as more abstract than the result
actually is, for an ML audience. The locked order is: transition in
words (without re-arguing novelty, already said once, early), give the
formula, then give the diagram, and only as the formula's
interpretation, not as the anchor.

1. **Transition in words**, pointing back to the formulation promised
   earlier, not re-arguing novelty (the "we do not claim..." move
   already happened once, in the Positioning Sentence, right after the
   Main Question — it does not repeat here):

   > The formulation promised above is the following identity.

2. **Formula**, the anchor of the whole paragraph:
   \[
   (S^F(p))^*=S^S(p^*).
   \]

3. **Plain-language restatement**, immediately after the formula,
   before any diagram:

   > Equivalently, dualizing after feature screening gives the same
   > representation as applying sample screening after dualizing.

4. **Diagram, last, as interpretation** — this is what makes the
   novelty visible, not what introduces the result:
   \[
   \begin{array}{ccc}
   p & \xrightarrow{S^F} & S^F(p)\\
   {\scriptstyle *}\big\downarrow & & \big\downarrow{\scriptstyle *}\\
   p^* & \xrightarrow{S^S} & S^S(p^*)
   \end{array}
   \]

This order, transition → formula → diagram-as-interpretation, applies
wherever the Main Theorem is presented: `doc1-intro.tex`'s Main Theorem
paragraph (not yet updated, see TODO — currently formula then one
sentence of interpretation, no diagram), and doc3's `\begin{theorem}[Dual
of screening]` Interpretation paragraph, where the diagram would fit
naturally as the theorem's required interpretation (per `style.md`'s
Interpretation Style rule) instead of prose alone. Note doc3's theorem
environment has no Main Question/Positioning Sentence before it (it is
mid-paper, not the introduction), so if the diagram is added there, a
short pointer back to the Positioning Sentence's claim may be useful
context — decide when doc3 is next touched.

## Result Hierarchy (locked 2026-07-04 — replaces the old "Theorem 1/2/3" numbering)

The authoritative ranking of every proved result, by narrative weight.
Nothing below should be described in prose as co-equal to the tier
above it. This also matches the actual `.tex` headers now (doc3's
subsections are named, not numbered: "Decomposition of Screening,"
"Duality of Screening," with Simultaneous Screening stated as a
`\begin{corollary}`, not a `\begin{theorem}`).

1. **Main result of the paper — Feature–Sample Duality** (Section 3,
   doc3 subsection "Duality of Screening"):
   \[
   (S^F(p))^* = S^S(p^*).
   \]
   This is the theorem the title sells.
2. **Framework laws — one per primitive** (Section 2, **locked
   2026-07-05**, see Section 2 Internal Order below). Section 2 does
   not study screening — it constructs the mathematical universe in
   which screening will later be defined: Fenchel–Rockafellar
   representations together with their primitive transformations.
   Each primitive gets exactly one structural law, and no theorem
   competes with another:
   ```
   FR representations
           │
           ▼
   Translation
           │
           ▼
   Fenchel Equivariance

   Restriction
           │
           ▼
   Commutativity
   ```
   - **Fenchel Equivariance** (translation's law):
     `(T_k(p))^*=T_{k^*}(p^*)`. This is what makes tier 1 provable.
   - **Commutativity** (restriction's law): `R^F_IR^S_J=R^S_JR^F_I`.
     Restriction acts on a different part of the representation than
     translation does, so this is restriction's structural law, exactly
     as Fenchel Equivariance is translation's. (Still stated without
     proof in doc2 — a one-line proof, since the two restrictions touch
     disjoint parts of `p` — see TODO; the positioning here is locked,
     the proof status is a separate, still-open bookkeeping item.)
   Neither law is itself the paper's contribution — both are machinery,
   the most important machinery, but still machinery.
3. **Structural theorem — Decomposition** (Section 3, doc3 subsection
   "Decomposition of Screening"):
   \[
   S^F=R^F\circ T^F,
   \qquad
   S^S=R^S\circ T^S.
   \]
   Not a destination — a structural characterization that tier 1's
   proof needs, and the fact that makes "Screening = Translation +
   Restriction" a theorem rather than a definition.
4. **Corollaries — attached locally to the result that produces them,
   never grouped into a shared "Consequences" subsection** (author's
   call, 2026-07-04: the paper narrates by logical dependency, not by
   result type):
   - **Intrinsic Complexity Reduction** attaches to §3.1
     (Definitions) — it needs only the two boxed definitions, nothing
     from tiers 2 or 3, so it is stated right there, before
     Decomposition even exists. Re-derived (for free, a remark, not a
     second corollary) once Decomposition is available in §3.2.
   - **Simultaneous Screening** attaches to §3.3 (Duality) — it needs
     tier 1 applied twice and nothing else, so it is stated in the same
     subsection as Duality, immediately after it, with no subsection
     break. This is the deliberate replacement for a Commutativity
     claim that turned out to be false in general.

Everything in Section 2 besides Fenchel Equivariance — the three
primitive translations (`T^d`,`T^v`,`T^s`), the two restriction
operators (`R^F`,`R^S`), the Abelian propositions, the conjugate and
regularity lemmas — is machinery in service of tier 2. None of it is
narrated as a result in its own right.

## Section-Level Roles (locked 2026-07-04)

- **Section 1 — Introduction** (revised 2026-07-05: leads with
  screening/ML, not with Fenchel calculus — Fenchel duality's role
  deliberately cut back relative to earlier drafts; **prose pass,
  2026-07-05: written out in full and no longer split into
  subsections** — `doc1-intro.tex` is now one continuous sequence of
  paragraphs under a single `\section{Introduction}`, no `\subsection`
  anywhere). Pose the question; resolve nothing technical. Logical
  flow (no longer literal headers, just the order of the prose):
  Background (screening in ML, historical development, with citations
  now wired in: `elghaoui2010safe`, `ogawa2014sample`,
  `shibagaki2016simultaneous`, `ndiaye2017gap`, `yamada2021dynamic`,
  `tran2025one`) → the Gap (both paradigms exploit convex duality but
  are formulated in model-specific, case-by-case ways; no common
  mathematical language relates them; boxed question replaced by a
  plain `quote` block, no `\boxed{}`) → **Positioning Sentence**
  (added 2026-07-05, third revision, applied to doc1): *"The goal of
  this paper is not to argue that feature screening and sample
  screening are dual. Rather, it is to formulate this apparent duality
  as a precise mathematical statement."* See Positioning Sentence
  above for the full rationale — this is the paper's one "no, but"
  move, stated exactly once, here, before Main Insight. → **Main
  Insight, reverted 2026-07-05 (third revision) to its technical
  content** — the 2026-07-05 second revision had turned Main Insight
  itself into the "no, but" move; that move now lives in the
  Positioning Sentence above, so Main Insight goes back to naming the
  actual mechanism, not repeating the positioning:

  > We introduce a common representation level on which both paradigms
  > are expressed as transformations of the same mathematical object,
  > so that Fenchel duality intertwines feature screening with sample
  > screening.

  → Why
  Is This Difficult? (primal fixed point vs. dual Fenchel–Young
  identity look unrelated) → Our Approach (framework as proof
  strategy, not contribution; FR model, the two screening formulas, and
  the dual-certificate interpretation, with the parameter-suppression
  aside moved into a `\footnote`) → main theorem (Feature↔Sample
  Duality, displayed unboxed) → Why Does It Matter? (consequences named,
  not detailed) → Main Contributions (now a prose paragraph naming the
  three tiers, not `\paragraph{Contribution N}` labels) → Organization
  (also prose, not an `itemize`). Three-sentence test anchors the whole
  section (see doc1's opening paragraph, which now states the gap as
  "model-specific, case-by-case" rather than "relationship unknown");
  the test itself is no longer presented as meta-commentary with an
  `enumerate` list, it *is* the opening paragraph. One-sentence
  encapsulation (synced 2026-07-05, third revision): *"In what
  mathematical sense are feature screening and sample screening dual
  to one another?"*, preceded in `doc1-intro.tex` by the historical
  lead-in *"However, this similarity has remained informal. Although
  the two paradigms appear to be dual, it remains unclear in what
  mathematical sense this duality should be understood."* The earlier
  "Is there a common mathematical framework..." wording is retired.
- **Section 2 — Fenchel–Rockafellar Representations and Their
  Transformations** (locked 2026-07-05 — this is the section title;
  doc2's actual `.tex` title matches exactly, confirmed 2026-07-05 —
  the file was renamed `doc2-group.tex` → `doc2-universe.tex` and
  rewritten into exactly the 3 locked subsections below). **Positioning
  (locked): Section 2 does not study screening. It
  constructs the mathematical universe in which screening will later be
  defined** — Fenchel–Rockafellar representations together with their
  primitive transformations. It answers exactly one question, **"What
  is the mathematical universe in which screening will be studied?"**,
  and answers it in three tiers, not as a flat list of definitions:
  ```
  Objects
      ↓
  Transformations
      ↓
  Structural laws
  ```
  Three subsections, each with a single role, a single "main law," and
  an insight that is the subsection's payoff line — nothing here is
  filler:

  **§2.1 — Fenchel–Rockafellar Representations.** *Role:* introduce the
  object. *Content:* FR representation, problem size, separability, why
  the constant `a` exists, and — the payoff — the **closure of FR
  representations under translation and restriction**. *Insight:* an FR
  representation is not just a way to write down a problem; it is
  designed to form a class *closed* under the transformations this
  paper studies. Drop `a` and translation (`T_k(p)=(\ldots,a+c)`) would
  produce a quadruple of a different shape than the one you started
  with — not closed.

  **§2.2 — Translation of FR Representations.** *Role:* introduce the
  first primitive transformation. *Content:* the three primitive
  translations, the translation action, the Fenchel dual, the dual
  translation, Fenchel Equivariance. *Main law:* **Fenchel
  Equivariance**, `(T_k(p))^*=T_{k^*}(p^*)`. *Insight:* translation is
  not just a transformation — it is compatible with Fenchel duality.

  **§2.3 — Restriction of FR Representations.** *Role:* introduce the
  second primitive transformation. *Content:* feature restriction,
  sample restriction, restriction's compatibility with translation,
  Commutativity, and the technical lemmas (conjugate of a separable
  restriction, separable sums preserve regularity). *Main law:*
  **Commutativity**, `R^F_IR^S_J=R^S_JR^F_I`. *Insight:* restriction
  acts on a different part of the representation than translation
  does — feature restriction touches `g` and `A`'s columns, sample
  restriction touches `f` and `A`'s rows — so the two restrictions
  commute.

  **Locked closing paragraph** (to replace doc2's Summary once this
  pass reaches doc2 — no notation table, no proof recap, one story):
  *"This section introduced the mathematical universe used throughout
  the paper: a class of Fenchel–Rockafellar representations together
  with two primitive transformations, translation and restriction. The
  two transformations satisfy their respective structural laws —
  Fenchel Equivariance and Commutativity — which provide the
  mathematical ingredients used in the next section to define screening
  and establish Feature–Sample Duality."*

  **Locked transition to Section 3.** A reader who has just been given
  Objects → Transformations → Structural laws naturally asks *"Where
  does screening fit into this picture?"* Section 3 opens by answering:
  screening is **not** a primitive transformation. It is a **derived**
  transformation obtained by combining translation and restriction —
  and only then does Definitions → Decomposition → Feature–Sample
  Duality follow.

  One-sentence encapsulation: *"We construct the mathematical setting —
  a closed class of representations together with their primitive
  transformations and structural laws — in which screening can be
  formulated."*
- **Section 3 — Duality Theory** (doc3; `.tex` section title already
  "Duality of Feature and Sample Screening" — matches). This is where
  the paper scores its points. **No "Consequences" subsection** — each
  corollary is narrated immediately after the result that produces it,
  by logical dependency, not grouped by result type (author's call,
  2026-07-04):
  ```
  3.1 Definitions (S^F, S^S)
      → Corollary: Intrinsic Complexity Reduction

  3.2 Decomposition (structural theorem)

  3.3 Duality (main theorem)
      → Corollary: Simultaneous Screening
  ```
  A reader never has to jump to a separate subsection to see what
  follows from what: Definitions produce the first corollary
  immediately; Duality produces the last one immediately.
  One-sentence encapsulation: *"Within this setting, screening is
  defined as a derived transformation, from which feature–sample
  duality follows."*

**Whole-paper narrative in three roles (locked):** Section 1 asks a
question. Section 2 builds a mathematical universe (objects +
transformations + laws). Section 3 defines screening in that universe
and proves the main theorem. No section overlaps another's job.

## 2026-07-03 (later pass): FR dual convention fixed, sign conflict resolved

The FR dual representation's constant is now **negated**:
`p^* = (g^*, f^*, -A^T, -a)` (previously `-A^T, a`, unchanged). This one
change, checked by direct computation, resolves *two* things flagged
earlier the same day:

1. **Restores the original `k^* = (-d,-c,-b)`.** An earlier pass in
   this file "corrected" `k^*` to `(-d,c,-b)` because, under the old
   `p^*` convention (`a` unchanged), `(-d,-c,-b)` gave a constant
   mismatch (`a+c` vs. `a-c`). That correction is now itself
   superseded: under the *new* `p^*` convention (`a` negated), the
   *original* `k^*=(-d,-c,-b)` is exactly what's needed — verified by
   direct computation (see Result Hierarchy tier 2's verification
   below).
2. **Resolves the sample-screening sign conflict.** Re-deriving
   Feature–Sample Duality under the new `p^*` convention forces the
   canonical sample-screening constant to be `-f_J̄^*(s)`, not
   `+f_J̄^*(s)`. This now **agrees** with the independent,
   optimization-motivated semantic derivation (Fenchel–Young equality
   at an assumed subgradient point, §3 Internal Order below) —
   previously these disagreed by a sign and were flagged as possibly
   two different operators. Verified by direct computation on both
   directions, unconditionally, for every `s`.

Both fixes verified by hand, twice each; still worth a second pair of
eyes given how central these results are, but no longer blocking.

**Verification of Fenchel Equivariance under the corrected convention:**
`T_k(p) = (T^d_bf,\,T^s_dg,\,A,\,a+c)`, so `(T_k(p))^* =
(T^d_{-d}(g^*),\,T^s_{-b}(f^*),\,-A^T,\,-(a+c))`. On the other side,
with `p^*=(g^*,f^*,-A^T,-a)` and `k^*=(-d,-c,-b)`: `T_{k^*}(p^*) =
(T^d_{-d}(g^*),\,T^s_{-b}(f^*),\,-A^T,\,-a+(-c))`. Both give constant
`-a-c`; every term matches.

## Notation Overhaul (2026-07-03, finalized)

Primitive translations are a **single family `T`**, distinguished only
by superscript, instead of three unrelated letters `D`, `V`, `S`:

- `T^d_b h := h(·+b)`, `b∈R^m` — domain translation (was `D_b`).
- `T^v_c h := h+c`, `c∈R` — value translation (was `V_c`).
- `T^s_d h := h+⟨d,·⟩`, `d∈R^n` — slope translation (was `S_d`).

Parameters are `b,c,d` (the components of `k=(b,c,d)`, unchanged),
**not** `a`/`α`, which would collide with the FR representation's own
constant `a` in `p=(f,g,A,a)`.

Restriction and screening carry the same two-tier convention: lowercase
roman superscript (`d`,`v`,`s`) always means a *primitive* translation
mode; uppercase (`F`,`S`) always means *feature*/*sample* — i.e. a
*derived*, screening-related object. `T^s` (slope) and `T^S` (sample)
are a deliberate, accepted case-sensitive pair — see Fixed Notation.

**`T^v` acts at the representation level inside `T^F`/`T^S`, not by
composing into `f`/`g` as a function.** Baking a constant into `f` and
then dualizing flips its sign (`(T^v_c f)^*=T^v_{-c}(f^*)`), while a
constant kept in the representation's own constant slot transforms
however the FR dual formula says the constant slot transforms (now:
negated — see above). These are different FR representations (same
optimization *problem*, different *quadruple*), and duality treats
them differently. `T^F_{I,z}` and `T^S_{J,s}` are defined as
representation-level actions `T_k` for the appropriate `k`; "`T^d` then
`T^v`" is read as "which two of the three primitives this `k` uses,"
not as literal function composition.

## Flagged Insight: Duality as a Third Transformation (2026-07-05, applied to doc2; paper.md sync still open)

**Applied, positioning still not fully resolved.** The author has since
restructured `doc2-universe.tex` into 4 subsections — FR
Representations, Duality, Translation, Restriction — with duality
treated explicitly as a third transformation under which the FR class
is closed, alongside translation and restriction (section title
shortened to "FR Representations and Transformations"). The class is
closed under duality via the Involution proposition (`(p^*)^*=p`),
now stated in its own `\subsection{Duality}`.

**New result added 2026-07-05: Restriction Equivariance**
(`prop:restriction-equivariance`, doc2's `\subsection{Restriction}`,
with a full proof, using Lemma "Conjugate of a separable restriction"):
```
(R^F_I(p))^* = R^S_I(p^*),   (R^S_J(p))^* = R^F_J(p^*).
```
This is restriction's counterpart to Fenchel Equivariance: dualizing a
feature restriction gives exactly a sample restriction, with the *same*
index set, on the dual representation (and symmetrically). Between
translation and restriction, both primitives now have a proved
compatibility law with duality — Fenchel Equivariance and Restriction
Equivariance — putting duality on genuinely equal footing with the
other two transformations, not just narratively.

**Done, same day:** doc3's Duality theorem proof was rewritten to cite
Decomposition, Fenchel Equivariance, and Restriction Equivariance as
three explicit, named steps, instead of one direct computation. The
two restriction/regularity lemmas ("Conjugate of a separable
restriction," "Separable sums preserve regularity") are still used, but
only to verify that the dual translation parameter produced by Fenchel
Equivariance coincides with the parameter that directly defines
screening on `p^*` — not to re-derive the whole tuple from scratch.
Both doc2 theorems' `\noteLE`s ("not cited by name") are updated to
reflect this.

**Still not decided:** whether duality gets its own tier-2 law
alongside Fenchel Equivariance and Commutativity in the Result
Hierarchy diagram (now plausibly three laws: Fenchel Equivariance for
translation, Restriction Equivariance *and* Commutativity for
restriction), whether Restriction Equivariance or Commutativity is
"the" law of the Restriction subsection or both are, and whether
"translation, restriction, and Fenchel Equivariance" (doc1's
Contribution 1) should be reworded. Section 2 Internal Order and the
Result Hierarchy below still describe the old 3-subsection, 2-law
picture and have not been swept to match — flagging rather than
rewriting immediately, since this touches locked positioning; reconcile
next time paper.md's Section 2 material is revised.

## Section 2 Internal Order (locked 2026-07-05)

Exactly three subsections — `doc2-universe.tex` matches this exactly
(confirmed 2026-07-05; restructuring done, see TODO for history).
Objects → Transformations → Structural laws; each subsection has one
role, one main law, and one payoff insight.

**§2.1 — Fenchel–Rockafellar Representations** (role: introduce the
object):
1. Define `p=(f,g,A,a)`, closed/proper/convex `f`,`g`, representing
   `p(x)=f(Ax)+g(x)+a`; problem size; separability.
2. State the closure property — the payoff of the subsection: this
   class is closed under translation and restriction (both map an FR
   representation to another FR representation of the same shape).
   This, not notational neatness, is why the constant `a` exists.

**§2.2 — Translation of FR Representations** (role: first primitive
transformation; main law: Fenchel Equivariance):
3. Define the three primitive translations `T^d`,`T^v`,`T^s` and
   package them into the translation action `T_k`.
4. Define the Fenchel dual `p^*=(g^*,f^*,-A^T,-a)` and the dual
   translation parameter `k^*=(-d,-c,-b)`.
5. **Law: Fenchel Equivariance.** `(T_k(p))^*=T_{k^*}(p^*)`, full
   proof. Insight: translation is compatible with Fenchel duality.

**§2.3 — Restriction of FR Representations** (role: second primitive
transformation; main law: Commutativity):
6. Define feature restriction `R^F_I` and sample restriction `R^S_J`;
   restriction's compatibility with translation; the two technical
   lemmas (conjugate of a separable restriction, separable sums
   preserve regularity) live here too.
7. **Law: Commutativity.** `R^F_IR^S_J=R^S_JR^F_I` — restriction's
   structural counterpart to Fenchel Equivariance. Insight: feature
   restriction touches `g` and `A`'s columns, sample restriction
   touches `f` and `A`'s rows — disjoint parts of `p`, so they commute.
   (Still stated without proof in doc2 — see TODO; a one-line proof,
   not resolved yet, separate from the positioning being locked here.)
8. Closing paragraph (locked wording — see Section-Level Roles above):
   the universe (representations + translation + restriction +
   their two laws) is exactly what Section 3 needs to define screening
   and establish Feature–Sample Duality.

**Role of each result, so nothing is narrated as "lost":**

| Piece | Gives |
|---|---|
| Representation | a closed universe |
| Translation | a primitive transformation |
| Fenchel Equivariance | translation's duality law |
| Restriction | a primitive transformation |
| Commutativity | restriction's composition law |

## Section 3 Internal Order

No "Consequences" subsection (author's call, 2026-07-04): each
corollary is narrated immediately after the result that produces it.
Steps below are tagged with the doc3 subsection they belong to.

**§3.1 — Feature and Sample Screening as Operators (Definitions):**

1. **Motivate from the optimization objective.** State
   `p(x)=f(Ax)+g(x)+a` for `p=(f,g,A,a)∈FR`. Screening simplifies this
   representation by eliminating a block of variables or loss terms;
   the structural calculus itself does not verify that this preserves
   the solution set — that is safe screening, future work.
2. **Feature screening, from an explicit assumption.** Assume every
   optimal solution satisfies `x_Ī=z`. Substituting gives
   `S^F_{I,z}(p)(x_I) = f(A_Ix_I+A_Ī z) + g_I(x_I) + a + g_Ī(z)`.
   Illustrated in doc3 by a Lasso example (`z=0`, translation trivial).
3. **Sample screening, from an explicit assumption.** Assume every
   optimal solution satisfies `s∈∂f_J̄(A_J̄x)`. By Fenchel–Young
   equality, `f_J̄(A_J̄x) = ⟨s,A_J̄x⟩ − f_J̄^*(s)`, giving
   `S^S_{J,s}(p)(x) = f_J(A_Jx) + g(x) + ⟨A_J̄^Ts,x⟩ + a − f_J̄^*(s)`.
   Illustrated in doc3 by a soft-margin SVM example (`s=0`, translation
   trivial, certifies a sample safely beyond the margin).
4. **Corollary: Intrinsic Complexity Reduction** — attaches here, not
   to a later "Consequences" section, because it needs only the two
   boxed definitions above (problem size `(m,|I|)` / `(|J|,n)`); no
   decomposition needed yet.

**§3.2 — Decomposition of Screening (structural theorem):**

5. **Structural theorem: Decomposition.** *Only after* both operators
   are defined semantically, prove `S^F=R^F∘T^F`, `S^S=R^S∘T^S` — the
   decomposition becomes the paper's structural insight, not an assumed
   definition. A short remark notes this re-derives step 4's corollary
   for free (not a second corollary, just a second proof of the same
   one).

**§3.3 — Duality of Screening (main theorem):**

6. **Main theorem: Duality.** `(S^F_{I,z}(p))^* = S^S_{I,z}(p^*)` and
   symmetrically. Feature and sample screening are not shown to commute
   as operators on the same `p` — they don't need to, since they are
   Fenchel-dual images of each other.
7. **Corollary: Simultaneous Screening** — attaches here, immediately
   after Duality, same subsection, no heading break: it needs Duality
   applied twice and nothing else. How a sample-then-feature
   composition on `p` relates, under duality, to a feature-then-sample
   composition on `p^*` — direct consequence of Duality applied twice.
   Replaces the earlier, incorrect Commutativity claim.

## Section Roadmap

| Section | Role | Purpose |
|---|---|---|
| 1. Introduction | Pose the question | Lead with screening/ML, not Fenchel calculus (revised 2026-07-05); state Main Insight before any framework; explain the obstacle; introduce the framework as proof strategy; preview the main theorem without proving it; state consequences without detailing them. |
| 2. Fenchel–Rockafellar Representations and Their Transformations (locked title; doc2's `.tex` title matches exactly, confirmed 2026-07-05) | Build the universe screening will live in — Objects → Transformations → Structural laws | §2.1 the FR representation, closed under translation and restriction (why `a` exists); §2.2 translation (`T^d`,`T^v`,`T^s`→`T_k`) and its law, Fenchel Equivariance; §2.3 restriction (`R^F`,`R^S`) and its law, Commutativity (proof status still open — see TODO). Does not define screening or answer the main question. |
| 3. Duality Theory (doc3, `.tex` title: "Duality of Feature and Sample Screening") | Score the paper's points | §3.1 define `S^F`,`S^S` semantically, immediately state Intrinsic Complexity Reduction (corollary); §3.2 prove Decomposition (structural theorem); §3.3 prove Duality (main theorem), immediately state Simultaneous Screening (corollary). No "Consequences" subsection — each corollary attaches to the result right above it. |

## Dependency Graph (paper-level)

FR representation `p=(f,g,A,a)` [Section 2 object, closed under both
branches below]
     │
     ├─→ Primitive translations (`T^d`, `T^v`, `T^s`) → Translation
     │    action (`T_k`)
     │    → **Fenchel Equivariance** (`(T_k(p))^*=T_{k^*}(p^*)`,
     │      `k^*=(-d,-c,-b)`) [Section 2 law — translation]
     │
     └─→ Feature restriction / Sample restriction (`R^F`, `R^S`)
          → **Commutativity** (`R^F_IR^S_J=R^S_JR^F_I`) [Section 2
            law — restriction; currently unproven, see TODO; a leaf —
            nothing in Section 3 currently cites it, unlike Fenchel
            Equivariance which Duality's proof needs directly]

Only the translation branch currently feeds forward into Section 3's
results below; the restriction branch's law (Commutativity) is
narrated for symmetry with translation's law, not because Section 3
depends on it yet.

→ Feature screening / Sample screening, defined semantically (doc3 §3.1)
     │
     ├─→ **Intrinsic Complexity Reduction** [corollary — needs only
     │    the definitions above, nothing below; doc3 §3.1]
     │
     └─→ **Decomposition** (`S^F=R^F∘T^F`, `S^S=R^S∘T^S`)
          [structural theorem; doc3 §3.2]
          │
          └─→ **Feature–Sample Duality** (`(S^F(p))^*=S^S(p^*)`)
               [main result; doc3 §3.3]
               │
               └─→ **Simultaneous Screening** [corollary — needs only
                    Duality applied twice; doc3 §3.3, same subsection]

The two corollaries are leaves off different points in this graph, not
a shared final stage — Intrinsic Complexity Reduction does not need
Decomposition or Duality, and is narrated before either exists.

## Fixed Notation

FR representation and its dual:

- FR representation: `p=(f,g,A,a)` — closed, proper, convex `f`,`g`;
  represents `p(x)=f(Ax)+g(x)+a`. The constant `a` exists so that this
  class is *closed* under translation and restriction (both map an FR
  representation to another one of the same shape) — see Section 2
  Internal Order above.
- Problem size: `(m,n)`.
- **Fenchel dual: `p^* = (g^*, f^*, -A^T, -a)`** (constant negated —
  changed 2026-07-03, see the fix note above), representing
  `p^*(y)=g^*(-A^Ty)+f^*(y)-a`. Involution: `(p^*)^*=p` (holds under
  both the old and the new convention — negating twice cancels either
  way, so this property alone couldn't distinguish them; the Duality
  theorem is what forced the choice).

Primitive translations (unified `T` family, replacing `D`/`V`/`S`):

- `T^d_b h := h(·+b)`, `b∈R^m` — domain translation.
- `T^v_c h := h+c`, `c∈R` — value translation.
- `T^s_d h := h+⟨d,·⟩`, `d∈R^n` — slope translation.
  **Case-sensitive pair, by design:** `T^s` (slope, lowercase roman)
  vs. `T^S` (sample screening family, uppercase) — visually close,
  worth a gut-check on a compiled page.

Translation action and derived translations:

- Translation parameter: `k=(b,c,d) ∈ R^m×R×R^n`.
- Translation action: `T_k : FR → FR`, `T_k(p) = (T^d_b f, T^s_d g, A,
  a+c)`.
- Dual translation: `k^* = (-d, -c, -b)` for `k=(b,c,d)` (restored to
  original, 2026-07-03).
- Feature translation: `T^F_{I,z} := T_{k^F_{I,z}}`, where
  `k^F_{I,z} := (A_Ī z, g_Ī(z), 0)` — domain+value, not slope. `T^v`
  acts on the representation's constant slot here, not by composing
  into `f` — see Notation Overhaul.
- Sample translation: `T^S_{J,s} := T_{k^S_{J,s}}`, where
  `k^S_{J,s} := (0, -f_J̄^*(s), A_J̄^T s)` — slope+value, not domain.
  Sign `-f_J̄^*(s)`, agreeing with both the canonical duality-forced
  value and the semantic Fenchel–Young derivation.

Restriction and screening:

- **Index notation (added 2026-07-05, doc2's `\subsection{Restriction}`,
  right before Feature/Sample restriction):** for `I⊆{1,...,n}`,
  `J⊆{1,...,m}`, and separable `g=Σg_i`, `f=Σf_j`: `x_I:=(x_i)_{i∈I}`,
  `g_I(x_I):=Σ_{i∈I}g_i(x_i)`, `f_J` symmetrically. For `A∈R^{m×n}`:
  `A_I:=A_{:,I}` (columns indexed by `I`), `A_J:=A_{J,:}` (rows indexed
  by `J`), and the combined block `A_{J,I}:=(A_J)_I=(A_I)_J`. The block
  notation `A_{J,I}` is not yet used by any proved result, but is what
  makes the cross-term in the Simultaneous Screening discussion
  (doc3 §3.3) precise — this is the exact `A_{J̄,Ī}` term that broke the
  earlier, dropped Commutativity theorem (see Open Problems history).
- Feature restriction: `R^F_I : FR → FR`, `R^F_I(f,g,A,a) =
  (f,g_I,A_I,a)`.
- Sample restriction: `R^S_J : FR → FR`, `R^S_J(f,g,A,a) =
  (f_J,g,A_J,a)`.
- Feature screening: `S^F_{I,z} := R^F_I ∘ T^F_{I,z} : FR → FR`.
- Sample screening: `S^S_{J,s} := R^S_J ∘ T^S_{J,s} : FR → FR`.

Complexity:

- intrinsic complexity, problem size.

## Fixed Terminology

- FR representation, Fenchel dual (involution).
- Primitive: domain translation, value translation, slope translation
  (`T^d`,`T^v`,`T^s`), translation action, feature restriction, sample
  restriction.
- Derived: feature translation, sample translation (`T^F`,`T^S`),
  feature screening, sample screening (`S^F`,`S^S`).
- Results, by tier (see Result Hierarchy): Fenchel equivariance and
  Commutativity (Section 2's two framework laws, one per primitive),
  Decomposition (structural theorem), Feature–Sample Duality (main
  result), Intrinsic Complexity Reduction and Simultaneous Screening
  (corollaries).

Feature-sample commutativity is **not** a property of this paper —
removed; Simultaneous Screening (a corollary, not a theorem) is the
correct replacement: composition on `p` relates to composition on
`p^*`, not to itself.

Do not write "Theorem 1/2/3" anywhere — the numbered scheme is
retired. Refer to results by name (Fenchel Equivariance, Decomposition,
Feature–Sample Duality) or by tier (main result / framework theorem /
structural theorem / corollary).

Banned synonyms and their exceptions: see `style.md` → Things That
Should Never Appear.

## Open Problems

- (none currently open. Resolved 2026-07-03: the sample-screening sign
  conflict — canonical `+f_J̄^*(s)` vs. semantic `-f_J̄^*(s)` — is fixed
  by negating the constant in the FR dual, `p^*=(g^*,f^*,-A^T,-a)`; both
  derivations now agree on `-f_J̄^*(s)`. Also resolved earlier the same
  day: the old Commutativity theorem's `A_{J̄,Ī}` cross-term gap, fixed
  by dropping that theorem in favor of Simultaneous Screening, which
  relates composition on `p` to composition on `p^*` instead of
  claiming commutativity on `p` itself.)

## TODO

- ~~Main Question re-revised, Positioning Sentence added, Main Insight
  reverted, Main Theorem Presentation updated with transition + diagram
  (2026-07-05, third revision)~~ — **done**, applied to
  `docs-new/doc1-intro.tex` in one pass. Gap paragraph now ends with
  the historical lead-in ("However, this similarity has remained
  informal. Although the two paradigms appear to be dual...").
  Boxed question (still the author's `center`/`emph` block, `\noteLE`
  kept) now reads "In what mathematical sense are feature screening
  and sample screening dual to one another?" Immediately after it, a
  new paragraph carries the Positioning Sentence ("The goal of this
  paper is not to argue... Rather, it is to formulate..."), with its
  own `\noteLE`; the existing "Main emphasis" paragraph (the
  model-specific/case-by-case signature sentence, still locked
  separately in Main Answer above) stays right after it, unchanged,
  before Main Insight. Main Insight replaced with the reverted
  technical wording. Main Theorem paragraph now opens with "The
  formulation promised above is the following identity," keeps the
  existing plain-language restatement, and ends with the commutative
  diagram. **Still open:** the same diagram could be added to doc3's
  `\begin{theorem}[Dual of screening]` Interpretation paragraph — not
  done yet, decide when doc3 is next touched.
- ~~Sync `docs-new/doc1-intro.tex`'s Organization-of-the-Paper
  paragraph to the locked hierarchy~~ — done as part of the 2026-07-05
  full revision below (no more "(Theorem~3)" anywhere in doc1).
- **`docs-new/doc1-intro.tex` revised 2026-07-05: leads with
  screening/ML, not Fenchel calculus.** Old standalone subsections "A
  Common Fenchel--Rockafellar Model," "Feature Screening," "Sample
  Screening" folded into a new "Our Approach: A Representation
  Framework" subsection, placed *after* new subsections "Main Insight"
  and "Why Is This Difficult?" — the FR formalism is no longer
  previewed before the gap is even stated. New opening paragraph adds a
  three-sentence test (see Section-Level Roles above) as the anchor for
  the whole section. Math content (FR model, screening formulas, main
  theorem) unchanged; only narrative order and framing changed.
  **Superseded 2026-07-05 (same day, prose pass, see below): every
  subsection mentioned in this entry no longer exists as a `\subsection`
  in the file** — kept here only as a record of the narrative-order
  decision, which still holds.
- **`meta/data.tex`'s `\paperAbstract` contradicts the resolved
  finding.** It still says "We further show that the two screening
  operators commute" — false in general (this is exactly the claim
  that was dropped in favor of Simultaneous Screening). Found
  2026-07-04 while checking the title against `meta/data.tex`; not
  fixed yet (out of scope for a paper.md/narrative.md-only pass) —
  flagging prominently since it's a real factual error in
  reader-facing text, not just a stale label. The abstract also still
  sells the framework ("we formulate screening operators through two
  primitive ingredients...") more than the locked positioning wants;
  worth a full rewrite once abstract work is in scope.
- ~~`docs-new/doc2-group.tex` restructured to the locked 2026-07-05
  positioning~~ — **done.** File renamed to `docs-new/doc2-universe.tex`
  (author's rename, `main.tex`'s `\input` updated to match) and
  rewritten into exactly the 3 locked subsections: §2.1
  Fenchel–Rockafellar Representations (now states the
  closure-under-translation-and-restriction justification for `a`
  explicitly, via an "Insight: a closed universe, not just a notation"
  paragraph); §2.2 Translation of FR Representations (merges the old
  Primitive Translation Operators / Translation Action / Fenchel
  Equivariance subsections); §2.3 Restriction of FR Representations
  (merges the old Restriction Operators subsection, keeping the two
  technical lemmas there). Section title is exactly
  "Fenchel–Rockafellar Representations and Their Transformations." The
  old Summary is replaced by the locked closing paragraph, verbatim.
  **Separate, still-open sub-item:** Commutativity is narrated
  (locked) as restriction's structural law, co-equal in role to
  Fenchel Equivariance, but is still stated without proof in doc2. The
  proof is one line (the two restrictions touch disjoint parts of
  `p`). Not resolved — decide whether to add the one-line proof when
  doc2 is next touched, or keep it explicitly flagged as unproven in
  that subsection.
- Apply the notation overhaul to `docs-new/doc2-universe.tex` — done
  2026-07-03 (kept for history): `p^*` negates the constant,
  `k^*=(-d,-c,-b)` restored, `D_b/V_c/S_d`→`T^d_b/T^v_c/T^s_d` (merged
  into one Definition environment), `k⊙p`→`T_k(p)`,
  `R^f_I/R^s_J`→`R^F_I/R^S_J`. Also added, previously missing:
  Proposition "Involution" (`(p^*)^*=p`) and Lemma "Separable sums
  preserve regularity" (needed by the Duality proof). `Restrictions
  commute` and `Restriction compatible with translation` kept without
  proof per author instruction — currently unused by any theorem,
  logged as such.
- Apply the notation overhaul to `docs-new/doc3-screening.tex` — done
  2026-07-03/04 (kept for history): full rewrite with `S^F/S^S`,
  `R^F/R^S`, `p^*=(g^*,f^*,-A^T,-a)`, sign `-f_J̄^*(s)`; Simultaneous
  Screening demoted from a numbered theorem to a corollary (author's
  call, 2026-07-04); Lasso and soft-margin-SVM examples added for
  feature and sample screening respectively.
- ~~`docs-new/doc1-intro.tex` revised 2026-07-05 for historical
  accuracy vs. the literature~~ — **done** (kept for history, second
  pass on doc1 the same day, after the screening/ML-first reorder
  above): Background split into "Screening in machine learning" +
  "Historical development" paragraphs; the Gap reworded from "different
  mathematical objects" to "model-specific... case-by-case basis, no
  common mathematical language" (matches `style.md`'s new Citing Prior
  Work rules); Main Question reworded to "Is there a common
  mathematical framework that explains these seemingly different,
  model-specific formulations?" (now the single source of truth, see
  Main Question above); new "Connection to dual certificates" paragraph
  using the non-reinterpretation phrasing instead of a "correction"
  framing; signature positioning sentence added to Main emphasis (see
  Main Answer above). Main Question, Section-Level Roles (Section 1),
  and this TODO entry are now synced to this wording as of 2026-07-05.
- ~~`docs-new/doc1-intro.tex` written out in full academic prose,
  2026-07-05~~ — **done.** The file was an annotated outline
  (`\paragraph{Goal.}` scaffolding, meta-commentary like "state that
  screening matters," commented-out citation-key placeholders) through
  every earlier pass; this pass replaced it with finished journal
  prose end to end, and removed every `\subsection` — the file is now
  one continuous sequence of paragraphs under a single
  `\section{Introduction}`. Section title changed from "Detailed
  Outline of the Introduction" to "Introduction," `\label{sec:intro}`
  added. Applied the 2026-07-04 Formatting Rules (`style.md`) for the
  first time on real content: the boxed Main Question and boxed Main
  Theorem are now plain (`quote` block / unboxed `\[ \]` display), and
  the "we suppress screening parameters" aside is now a `\footnote`
  instead of a loose sentence. The three previously-commented citation
  keys are now live: `elghaoui2010safe`, `ogawa2014sample`,
  `shibagaki2016simultaneous` in the historical-development paragraph,
  plus `ndiaye2017gap`, `yamada2021dynamic`, `tran2025one` for
  FR-duality-derived methods. Math content is unchanged from the prior
  outline; only presentation changed. See Section-Level Roles (Section
  1) above for the updated flow description.
- Confirm the "safe screening" framing in `docs-new/doc1-intro.tex`
  still matches once Section 1 gets a full prose pass — now even more
  natural, since sample screening's structural constant `-f_J̄^*(s)` is
  literally the Fenchel–Young minorant value, matching the
  safe-screening literature's certificate directly.
