# Review Checklist

Run through this before treating any section as done. Rules live in
`agent.md`/`style.md`/`paper.md`; this file only checks them.

## Structure

- [x] Section 1 (`doc1-intro.tex`): single `\section{Introduction}`,
      no `\subsection`; logical flow only, in order: Background, The
      Gap, Main Question, Positioning Sentence, Main Insight, Why Is
      This Difficult?, Our Approach, Main Theorem, Why Does It Matter?,
      Main Contributions, Organization. Not re-verified in the
      2026-07-05 doc2/doc3 sync — re-check before relying on this.
- [x] Section 2 (`doc2-universe.tex`), title "FR Representations and
      Transformations": exactly 4 subsections (FR Representations,
      Duality, Translation, Restriction), one law each (Involution,
      Translation Duality, Restriction Duality); no screening defined
      here; no Commutativity anywhere.
- [x] Section 3 (`doc3-screening.tex`), title "Duality of Feature and
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
- [x] doc3 swept to `Γ_{m,n}` everywhere (2026-07-05); the undefined
      `mathcal{FR}^{sep}_{m,n}` symbol no longer appears anywhere.

## Style (`style.md`)

- [x] No `\boxed{}` anywhere in doc1/doc2/doc3 (2026-07-05: last
      occurrence, Translation Duality's statement in doc2, removed).
- [x] No dashes (`-`, `--`, `---`) as prose punctuation in doc1/doc2/
      doc3 (2026-07-05: doc2's remaining Motivation-paragraph dashes
      fixed). "Fenchel--Rockafellar" / "Fenchel--Young" en-dash naming
      convention is not affected by this rule.
- [ ] No bolded opening word(s) of a paragraph.
- [ ] No banned words: "raw size/complexity", hedging filler
      ("obviously", "clearly", "indeed", "very", "actually").
- [ ] Every theorem has Intuition, Statement, Proof idea, Discussion;
      every main theorem ends with an interpretation.
- [ ] Prior-work citations follow the non-correction framing (see
      style.md "Citing Prior Work"); no "Author X did Y, but actually
      did Z."
- [ ] Paragraph Structure, Claim Discipline, Mathematical Prose, and
      Examples rules (style.md, added 2026-07-05) applied to doc2/doc3,
      not yet spot-checked.

## Known Open Items (check still applies before closing a pass)

- [ ] `meta/data.tex`'s `\paperAbstract` still says the two screening
      operators commute — false, not yet fixed.
- [x] doc3's Duality theorem now has a commutative diagram in its
      Interpretation paragraph (added 2026-07-05), matching doc1's
      Main Theorem presentation.
- [x] doc3 line 4 typo fixed: "FR representtaion" → "FR representation."
- [ ] `(g_I)^*=(g^*)_I` and sub-block regularity are stated as "basic
      convex-analysis facts" in doc2/doc3 without a citation; author
      intends to add one before submission.

## Before Compiling

- [ ] `main.tex`'s `\input` lines match the current file names
      (`doc1-intro`, `doc2-universe`, `doc3-screening`).
- [ ] No undefined `\ref`/`\label` (check `latexmk` warnings).
- [x] `agent/paper.md` and `agent/narrative.md` reflect the actual
      `.tex` files (synced 2026-07-05 against doc2/doc3; doc1 not
      re-verified this pass).
