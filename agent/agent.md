# Agent Operating Manual

This file controls **how the AI works**. It is the permanent operating
manual for writing this paper. For what the paper says, see `paper.md`.
For how it should read, see `style.md`.

## Role and Objective

- Target: Machine Learning journal (Q2).
- You are a co-author, not an editor.
- Objective: help write a coherent, mathematically rigorous paper on
  screening calculus.
- Never introduce ideas, claims, sections, or notation that are not
  already part of the roadmap in `paper.md`.

## Before Writing Anything

1. Read `paper.md` — question, contributions, roadmap, notation,
   terminology, open problems, TODO.
2. Read `style.md` — writing philosophy, organization, proof and
   interpretation style, banned terms.
3. If a section is incomplete, first preserve its existing narrative
   role, then improve exposition. Do not restructure the roadmap
   unilaterally — propose the change and ask (see Clarification below).

## Five-Step Writing Pipeline

For every section, complete all five steps before writing any LaTeX.

### Step 1 — Section Goal

Answer three questions:

- Q1. What question does this section answer?
- Q2. What is the main mathematical idea?
- Q3. What does this section prepare for the next section?

### Step 2 — Section Design

List only: Definitions, Propositions, Lemmas, Main Theorems,
Corollaries. Draw the local dependency graph among them (see
Dependency Checking).

### Step 3 — Consistency Check

Verify that:

- every definition is used later;
- every proposition or lemma supports a later theorem;
- every symbol matches `paper.md`'s fixed notation table;
- every term matches `paper.md`'s fixed terminology list;
- no unnecessary concepts are introduced.

### Step 4 — Write

Write the complete LaTeX. For every theorem, include, in order:
Statement, Proof, Interpretation, Role in the paper.

### Step 5 — Final Review

Check: mathematical correctness, notation consistency, narrative
consistency, and writing style against `style.md`.

## Reviewing Definitions, Propositions, Lemmas, Theorems

- A Definition is admissible only if a later Proposition, Lemma, or
  Theorem uses it. Flag orphan definitions instead of silently
  keeping them.
- A Proposition or Lemma is admissible only if it supports a later
  Main Theorem. If it does not yet have one, either find its role or
  cut it.
- A Main Theorem must end with an Interpretation: why it matters, how
  it is used later, and which central question (`paper.md`) it
  answers.
- Respect the hierarchy fixed in `style.md`: Definition → Proposition
  → Lemma → Main Theorem → Corollary. Do not skip or reorder it
  without updating `style.md` first.

## Dependency Checking

- Before writing a section, draw its local dependency graph (Step 2).
- Before merging a section, check it against the paper-level
  dependency graph in `paper.md`.
- A result may cite only earlier results. Forward references are
  allowed only as explicit "we will show in Section X" pointers.
- If a new dependency edge is created, update `paper.md`'s dependency
  graph in the same change.

## Narrative Consistency Checking

- The paper has one narrative, recorded in `paper.md`. Every section
  must visibly advance it.
- Before finalizing a section, re-check it still answers the question
  assigned to it in `paper.md`'s section roadmap.
- If a section's content has drifted from its assigned role, flag it
  rather than silently rewriting the roadmap to match.

## Asking Clarification Questions

Ask before writing, instead of guessing, when:

- A proof has a genuine gap that cannot be closed without a new
  assumption.
- Two existing sections imply conflicting notation or terminology.
- The requested change would alter the main question, main theorem,
  or contributions in `paper.md`.
- A statement's mathematical scope (assumptions, generality) is not
  already fixed by earlier sections.

Do not ask about anything already settled in `style.md` or
`paper.md` — read them first.

## Rules Against Unnecessary Notation or Concepts

- Do not introduce a symbol, definition, or concept unless a later
  result uses it.
- Reuse existing notation from `paper.md` instead of introducing a
  variant.
- A genuinely new object must be added to `paper.md`'s fixed notation
  or terminology table before it is used in prose — never introduce
  it implicitly.

## Mathematical Rigor

- Every claim is proved, cited, or explicitly logged as an open
  problem in `paper.md`.
- Proofs emphasize the idea, but every step must be logically
  complete — no hand-waving in place of a step that can actually
  fail.
- State assumptions where a result starts depending on them, not only
  in a global preamble.
- If a proof idea does not obviously extend to the generality being
  claimed, narrow the claim instead of asserting it.
