# Review Checklist

Run through this before treating any section as done. Rules live in
`agent.md`/`style.md`/`paper.md`; this file only checks them.

## Structure

- [x] Section 1 (`doc1-intro.tex`): single `\section{Introduction}`,
      no `\subsection`; logical flow, in order: Context,
      Classification, Scope, Historical development, Tension and gap,
      boxed Q1+Q2, Central idea, Class of problems, Class of objects
      (screening restated), Structural insight, Answer to Q2,
      Contributions, Organization. Verified 2026-07-05 against the
      current file. No separate Positioning Sentence, "Why Is This
      Difficult?", or "Why Does It Matter?" beats anymore — confirmed
      intentional and final by the author.
- [x] Section 2 (`doc2-universe.tex`), title "FR Representations and
      Equivariant Transformations": exactly 4 subsections (FR
      Representations, FR Duality, Translation, Restriction), one law
      each (Involution, Translation Duality, Restriction Duality); no
      screening defined here; no Commutativity anywhere.
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
- [ ] Fenchel/FR terminology locked 2026-07-05 (`style.md`): FR
      representation / FR duality / Fenchel conjugate / Fenchel--Young
      equality never substituted for each other; "Fenchel--Rockafellar"
      spelled out in full only twice total (abstract, intro's first
      use), "FR" everywhere else. Known current violations in doc2/doc3
      not yet swept — see `paper.md`'s TODO.
- [x] doc3 uses `Γ_{m,n}` everywhere; the undefined
      `mathcal{FR}^{sep}_{m,n}` symbol does not appear anywhere
      (re-verified 2026-07-05).
- [x] All citation keys introduced in the current `doc1-intro.tex`
      (21 keys, see `paper.md`'s Section 1 role entry) exist in
      `meta/refs.bib` (checked 2026-07-05).

## Style (`style.md`)

- [x] No `\boxed{}` anywhere in doc1/doc2/doc3.
- [x] No dashes (`-`, `--`, `---`) as prose punctuation in doc1/doc2/
      doc3. "Fenchel--Rockafellar" / "Fenchel--Young" en-dash naming
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
      Examples rules (style.md) applied to doc2/doc3, not yet
      spot-checked.
- [ ] "Optimal solution" / "at the optimum" / "at optimality" banned
      language: doc3's §3.1 uses "certified to vanish at the optimum"
      / "certified... at the optimum" only when explicitly describing
      prior literature's own framing (style.md's exception) — spot
      check doc1 similarly if its wording changes again.

## Known Open Items (check still applies before closing a pass)

- [x] `meta/data.tex`'s `\paperAbstract` no longer claims the two
      screening operators commute (rewritten; re-verified 2026-07-05).
- [x] doc3's Duality theorem has a commutative diagram in its
      Interpretation paragraph, matching doc1's Main Theorem
      presentation.
- [x] doc3's Decomposition-subsection closing remark now credits both
      Translation Duality and Restriction Duality (fixed 2026-07-05).
- [ ] `(g_I)^*=(g^*)_I` and sub-block regularity are stated as "basic
      convex-analysis facts" in doc2/doc3 without a citation; author
      intends to add one before submission.
- [x] Positioning Sentence removal and the two-question (Q1, Q2)
      wording both confirmed final by the author, 2026-07-05.

## Before Compiling

- [ ] `main.tex`'s `\input` lines match the current file names
      (`doc1-intro`, `doc2-universe`, `doc3-screening`).
- [ ] No undefined `\ref`/`\label` (check `latexmk` warnings).
- [x] `agent/paper.md` and `agent/narrative.md` reflect the actual
      `.tex` files and `meta/data.tex` (synced 2026-07-05 against
      doc1/doc2/doc3 and the abstract).
