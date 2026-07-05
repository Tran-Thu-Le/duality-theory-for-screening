# Writing and Presentation Principles

This file controls **how the paper is written**: prose style, but also
narrative logic, claim discipline, and proof structure. Content lives
in `paper.md`, working process lives in `agent.md`.

## Narrative (summary)

One narrative throughout the paper: translation and restriction are
each equivariant under Fenchel--Rockafellar duality (Translation
Duality, Restriction Duality); feature and sample screening decompose
into these two primitives, and are therefore themselves equivariant
under FR duality, feature screening on a primal representation
answering to sample screening on its dual. Full question, roadmap, and
contributions: see `paper.md`.

## Writing Philosophy

- Every section answers one mathematical question.
- Every definition exists for a later theorem.
- Every proposition supports a later theorem.
- Every theorem must include an interpretation.
- Every section ends with a short summary explaining its role.
- Keep one narrative throughout the paper.
- Avoid survey-style writing in the body.
- Use concise theorem statements.
- Proofs emphasize ideas rather than calculations.

## Paragraph Structure

- Every paragraph communicates one mathematical idea.
- The first sentence states the main point; the rest justify, explain,
  or prepare the next idea.
- Never mix motivation, definition, and interpretation in one
  paragraph.
- A paragraph that does this well makes the reader want the next one;
  that is a consequence of following the rule above, not a separate
  check to run.

## Audience and Tone

- Audience: researchers in optimization and machine learning.
- Tone: application-oriented, mathematical, insight-driven.
- Average sentence length 15-20 words.

## Section Organization

Every subsection contains, in order: Motivation, Definition, Insight,
Transition.

- **Motivation** explains why the next object is necessary. In
  Section 1 (Introduction), motivation may be historical (screening's
  development in the literature). In Sections 2-3 (the technical
  body), motivate by the mathematical gap in the current narrative,
  not by history: what does the reader already have, and what can they
  not yet do with it.
- **Insight** states what is mathematically new about the object just
  introduced, not how its proof or construction works.
- **Transition** explains why the next subsection is unavoidable, not
  merely that it comes next.
  - Avoid: *"We next define sample screening."*
  - Prefer: *"Feature screening acts on primal variables. Its dual
    counterpart requires a different assumption, leading to the
    following definition."*

## Theorem Organization

Hierarchy: Definition → Proposition → Lemma → Main Theorem →
Corollary.

Every theorem entry contains, in order: Intuition, Statement, Proof
idea, Discussion.

## Proof Style

- Emphasize the idea, not the calculation.
- State the key step before executing it.
- Push routine or mechanical computation to a remark, or omit it.

## Mathematical Prose

- Mathematics appears only when it advances the narrative.
- Display an equation only when it defines a new object, states a
  theorem, or expresses a key idea. Routine substitutions stay inline.
- Avoid displaying an equation that merely restates the surrounding
  prose.

## Examples

- An example illustrates the meaning of a definition; it is not a
  miniature proof.
- Emphasize why the example is representative, how it fits the
  framework, and what insight it provides.
- Avoid routine calculations that do not serve one of those three
  purposes.

## Interpretation Style

Every main theorem ends with a short interpretation explaining:

- Why the theorem matters.
- Why it was not obvious.
- How it is used later.
- Which central question it answers.

The interpretation never repeats the theorem statement in different
words; if it has nothing to add beyond "why/how/which," it is not
ready to write.

## Claim Discipline

- Never overclaim. Every claim about the paper's own results must be
  directly supported by a theorem, proof, or citation.
- Prefer verbs that match what was actually shown: "shows,"
  "establishes," "admits," "provides." Avoid verbs that claim more
  than the result delivers: "solves," "completely characterizes,"
  "unifies everything."
- This is about claims the paper makes about itself; see "Citing Prior
  Work" above for claims about other authors' work.

## Notation Rules

- Use only the notation fixed in `paper.md`. Never invent a new
  symbol in prose.
- A new object must first be added to `paper.md`'s fixed notation
  table, then used.
- One symbol, one meaning — notation is never redefined mid-paper.

## Terminology Rules

- Use only the terms fixed in `paper.md`. Never introduce a synonym
  for an existing fixed term.
- Always distinguish "screening" (the structural theory) from "safe
  screening" (the applied literature that motivates it, discussed
  only as motivation and future work, not as a contribution).
- Do not use "optimal solution," "at the optimum," or "at optimality"
  when stating this paper's own definitions or assumptions. This paper
  studies screening structurally, not safe screening: the assumptions
  behind `S^F`, `S^S` (e.g. `x_Ī=z`, `s∈∂f_J̄(A_J̄x)`) are stated as
  direct, hypothetical relations on `p`, not as properties of an
  optimal solution or a certificate. This phrasing is acceptable only
  when explicitly describing prior literature's own framing (e.g. "in
  the literature, feature screening typically eliminates a block of
  primal variables certified to vanish at the optimum").

## Fenchel / FR Terminology (locked 2026-07-05)

Four distinct terms, never used for each other's meaning:

- **FR representation** — the quadruple `p=(f,g,A,a)`. Never "Fenchel
  representation."
- **FR duality** — the transformation `p ↦ p^*=(g^*,f^*,-A^T,-a)` on
  representations. Never "Fenchel duality" when this transformation is
  meant.
- **Fenchel conjugate** — only for the conjugate of a single function,
  `f^*`, `g^*` (or `h^*` in general). Never used for the
  representation-level transformation above.
- **Fenchel--Young equality** — only for the identity
  `f(y)+f^*(s)=\langle s,y\rangle` (equivalently `s\in\partial f(y)`).
  Never a stand-in for FR duality or the Fenchel conjugate.

**Fenchel--Rockafellar, spelled out in full, is written exactly twice
in the whole paper: once in the abstract, once in the introduction (its
first appearance, where the abbreviation FR is introduced).** Every
other occurrence, in every section, including the rest of the
introduction, is abbreviated "FR." This applies to both "FR
representation" and "FR duality." Do not spell out
"Fenchel--Rockafellar" a second time anywhere, including inside
theorem/definition/proof environments in doc2 or doc3.

## Citing Prior Work (added 2026-07-05)

- Never frame a reinterpretation of prior work as a correction —
  avoid constructions like "Author X did Y, but actually did Z." Even
  when the framework gives a cleaner reading of an existing method
  (e.g., a dual certificate as a fixed slope via Fenchel--Young), state
  it as an interpretation the framework *admits*, not as what the
  original authors "really" did.
  - Avoid: *"Ogawa fixed dual variables, but actually he fixed
    slopes."*
  - Prefer: *"Within our framework, the dual certificates used in
    sample screening admit a natural interpretation as fixing
    supporting slopes via the Fenchel--Young identity."*
- When motivating the gap the paper addresses, avoid overly strong
  claims a reviewer can refute in one sentence (e.g., "they use
  different mathematical objects" — both provably use convex duality).
  Prefer precise, defensible framing: existing methods are
  "model-specific" and derived "on a case-by-case basis," not built on
  a common mathematical language — that absence, not a claimed
  difference in kind, is the actual gap.
- This paper does not compete with or supersede prior screening rules
  (Ghaoui, Ogawa, Shibagaki, etc.). It operates one level up: it does
  not derive a new screening rule, it identifies the common
  mathematical structure underlying derivations that were each built
  model-by-model. Keep this positioning explicit whenever the paper's
  goal is restated.

## Formatting Rules (added 2026-07-04)

- Never box a formula, even a main result — no `\boxed{}`.
- Never use dashes (`-`, `--`, `---`) in running prose.
- Never bold the opening word(s) of a paragraph.
- Tone stays academic, insight-driven, and concise throughout.

## Things That Should Never Appear

- "raw size", "raw complexity" — use "problem size" / "intrinsic
  complexity" instead.
- "reduction" as a bare synonym for screening — allowed only when
  explicitly referring to complexity reduction (e.g., "screening
  rules reduce the intrinsic complexity").
- Hedging filler: "obviously", "clearly", "indeed", "very", "actually".
- Prefer instead: "therefore", "instead", "consequently", "thus".
- "consider" as a throat-clearing opener ("Consider the following
  problem...") — state the object directly instead. "introduce,"
  "define," "construct" remain standard and acceptable.

## Consistency Rules

- A term or symbol introduced in one section is used identically in
  every later section.
- Any change to notation or terminology is made in `paper.md` first,
  then propagated through the draft.
- If `style.md` and `paper.md` ever appear to conflict: `paper.md`'s
  fixed tables win for notation and terminology; `style.md` wins for
  prose, organization, and proof rules.
