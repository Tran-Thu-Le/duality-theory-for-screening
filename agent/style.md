# Writing Style

This file controls **how the paper is written**. It fully determines
style; content lives in `paper.md`, working process lives in
`agent.md`.

## Narrative (summary)

One narrative throughout the paper: primitive translations and
coordinate restrictions combine, via Fenchel Equivariance, into
feature and sample screening, which are dual under the Fenchel
transform. Full question, roadmap, and contributions: see `paper.md`.

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

## Audience and Tone

- Audience: researchers in optimization and machine learning.
- Tone: application-oriented, mathematical, insight-driven.
- Short paragraphs. Average sentence length 15-20 words.

## Section Organization

Every subsection contains, in order: Motivation, Definition, Insight,
Transition.

## Theorem Organization

Hierarchy: Definition → Proposition → Lemma → Main Theorem →
Corollary.

Every theorem entry contains, in order: Intuition, Statement, Proof
idea, Discussion.

## Proof Style

- Emphasize the idea, not the calculation.
- State the key step before executing it.
- Push routine or mechanical computation to a remark, or omit it.

## Interpretation Style

Every main theorem ends with a short interpretation explaining:

- Why the theorem matters.
- How it is used later.
- Which central question it answers.

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

## Consistency Rules

- A term or symbol introduced in one section is used identically in
  every later section.
- Any change to notation or terminology is made in `paper.md` first,
  then propagated through the draft.
- If `style.md` and `paper.md` ever appear to conflict: `paper.md`'s
  fixed tables win for notation and terminology; `style.md` wins for
  prose, organization, and proof rules.
