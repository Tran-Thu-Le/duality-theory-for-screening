# Review Checklist

Run through this before treating any section as done. Rules live in
`agent.md`/`style.md`/`paper.md`; this file only checks them.

## Structure

- [x] Section 1 (`doc1-intro.tex`): single `\section{Introduction}`,
      no `\subsection` (removed 2026-07-05, full prose pass);
      logical flow only, in order: Background, The Gap, Main Insight,
      Why Is This Difficult?, Our Approach, Main Theorem, Why Does It
      Matter?, Main Contributions, Organization.
- [ ] Section 2 (`doc2-universe.tex`), title "Fenchel--Rockafellar
      Representations and Their Transformations": exactly 3
      subsections (Representations, Translation, Restriction); no
      screening defined here.
- [ ] Section 3 (`doc3-screening.tex`), title "Duality of Feature and
      Sample Screening": exactly 3 subsections (Screening as
      Operators, Decomposition, Duality); no separate "Consequences"
      subsection — corollaries attach to the result that produces
      them.

## Notation and Terminology

- [ ] Every symbol used already appears in `paper.md`'s Fixed
      Notation table.
- [ ] No "Theorem 1/2/3" numbering anywhere — results named by role.
- [ ] `p^*=(g^*,f^*,-A^T,-a)`, `k^*=(-d,-c,-b)` used consistently.
- [ ] "Screening" vs. "safe screening" kept distinct.

## Style (`style.md`)

- [ ] No `\boxed{}` around any formula.
- [ ] No dashes (`-`, `--`, `---`) in running prose.
- [ ] No bolded opening word(s) of a paragraph.
- [ ] No banned words: "raw size/complexity", hedging filler
      ("obviously", "clearly", "indeed", "very", "actually").
- [ ] Every theorem has Intuition, Statement, Proof idea, Discussion;
      every main theorem ends with an interpretation.
- [ ] Prior-work citations follow the non-correction framing (see
      style.md "Citing Prior Work"); no "Author X did Y, but actually
      did Z."

## Known Open Items (check still applies before closing a pass)

- [ ] `meta/data.tex`'s `\paperAbstract` still says the two screening
      operators commute — false, not yet fixed.
- [x] `doc1-intro.tex` retrofitted to the 2026-07-04 Formatting Rules
      (2026-07-05, full prose pass): no boxed formulas, no dashes,
      no bolded paragraph openers.
- [ ] `doc2-universe.tex`, `doc3-screening.tex` were written before
      the 2026-07-04 Formatting Rules (boxed formulas, dashes) — not
      yet retrofitted.
- [ ] Commutativity proposition (`doc2-universe.tex`, S2.3) still
      stated without proof, by author instruction.

## Before Compiling

- [ ] `main.tex`'s `\input` lines match the current file names
      (`doc1-intro`, `doc2-universe`, `doc3-screening`).
- [ ] No undefined `\ref`/`\label` (check `latexmk` warnings).
- [ ] `agent/paper.md` and `agent/narrative.md` reflect the actual
      `.tex` files, not a stale prior draft.
