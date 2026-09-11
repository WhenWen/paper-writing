# Paper timelines and checklists

Use the parts relevant to the current stage. Do not burden an early outline with camera-ready formatting checks.

## Suggested deadline rhythm

For a fixed submission deadline, a useful target is:

- **Four weeks before:** main theoretical or empirical results exist; the paper has a ten-sentence story, terminology, running example, planned figures, and claim--evidence outline.
- **Two weeks before:** every section has a complete draft; missing results are explicit rather than hidden in prose.
- **One week before:** the paper could be uploaded; compilation, page limits, references, and supplementary structure work end to end.
- **Three days before:** freeze major story changes when possible; focus on correctness, consistency, visual inspection, and small edits.
- **Until submission:** exchange full reads with collaborators, prioritizing readers unfamiliar with the derivation history.

Treat this as planning guidance, not a reason to conceal a serious late-discovered error.

## Before prose drafting

- [ ] The central question and contribution fit in a story spine of at most ten sentences.
- [ ] Claims are separated into theorem, empirical observation, hypothesis, and conjecture.
- [ ] A small, consistent vocabulary names the main concepts.
- [ ] One or two concrete running examples are selected.
- [ ] The opening figure or graphical abstract is planned.
- [ ] Every planned experiment answers a question and has an adequate control.
- [ ] Every major theorem has an understandable message and a plausible proof skeleton.
- [ ] A hierarchical claim--evidence outline exposes logical gaps.

## Structural audit

- [ ] Title is distinctive and no broader than the contribution.
- [ ] Abstract states the tension, idea, evidence, and result in one coherent paragraph.
- [ ] Introduction asks and answers the paper's main question.
- [ ] Paragraph openings alone recover a reasonable summary.
- [ ] Each section and subsection has one communicative job.
- [ ] Terminology and notation are stable.
- [ ] Important definitions appear before substantive use and are recalled after long gaps; necessary advance mentions follow the Cref strategy.
- [ ] Comments and remarks follow their supporting definitions, except in genuine introduction or section-overview previews.
- [ ] Theorems are followed by interpretation and proof pointers.
- [ ] Lemma statements and adjacent prose reveal the proof plan.
- [ ] Experiments are organized by claims or questions, not chronology.
- [ ] Claims have evidence at the appropriate scale and under fair comparisons.
- [ ] Figures and captions can be skimmed independently.
- [ ] Limitations identify real boundaries.

## Technical and visual audit

- [ ] The paper compiles without unresolved references, citations, or material warnings.
- [ ] Links work and point to the intended targets.
- [ ] No equation, table, algorithm, or figure overflows margins.
- [ ] Main theorem and algorithm statements have received a dedicated typo and symbol pass.
- [ ] Figure fonts, legends, labels, lines, units, and axis limits remain readable at final size.
- [ ] Comparable plots use comparable scales or explain why not.
- [ ] Mathematical displays have grammar and punctuation.
- [ ] Notation needed for current reasoning is defined locally; necessary deferred mentions follow the Cref strategy and point to verified definitions.
- [ ] Citation commands are grammatical and citation tone is precise.
- [ ] Venue style, page limit, bibliography format, subject area, and supplementary rules are checked against current instructions.
- [ ] Title and abstract in the submission system match the PDF.

## Anonymity and reproducibility

- [ ] PDF metadata, acknowledgments, comments, file paths, repository links, and supplementary files do not reveal identity when review is anonymous.
- [ ] Shared code excludes generated files that can embed usernames or local paths, including bytecode where relevant.
- [ ] Search the release for author names, usernames, institutions, absolute paths, API keys, and private URLs.
- [ ] Code, data, configuration, and seeds needed to reproduce the main result are present or their absence is disclosed.
- [ ] The paper describes compute accounting, tuning budget, and evaluation protocol sufficiently for the claim.

## arXiv release

- [ ] Incorporate accepted-review feedback and re-audit the main claims.
- [ ] Use a readable conference-neutral format when appropriate; remove submission-only compression tricks.
- [ ] Polish appendix transitions and proof structure; move important material into the main body if space no longer forces it out.
- [ ] Recheck recent and broader related work without adding citations merely for volume.
- [ ] Add acknowledgments, funding, and accepted/published status when applicable.
- [ ] Add code and project links in both the paper and repository README when public.
- [ ] Remove author comments and clean the source package without breaking references or links.
- [ ] Verify the arXiv category and metadata with coauthors.
- [ ] Render and visually inspect the uploaded source result rather than assuming local compilation is identical.
