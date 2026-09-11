---
name: paper-writing
description: Plan, draft, revise, simplify, or audit machine-learning and mathematical research papers. Use for paper stories and outlines, redundant prose, titles, abstracts, introductions, methods, experiments, theorem and proof exposition, figure captions, LaTeX prose, and submission checks; do not use for ordinary nontechnical or creative prose.
---

# Paper Writing

Produce a paper that is easy to skim, hard to misread, and possible to verify. An expert should recover the main story from the title, abstract, introduction, main results, and figure captions. A careful reader should find the definitions, assumptions, evidence, and reproducibility details needed to check it.

## Compress the paper at each level

**The introduction is a lossy compression of the full paper. The abstract
is a further lossy compression of the introduction.** Preserve the most
important problem, idea, mechanism, results, and implications at each level.
Omit secondary detail while retaining the assumptions and qualifications
needed to keep the retained claims true. Each shorter version must remain
self-contained and preserve the author's emphasis.

When rewriting an abstract from an author-revised introduction, use that
introduction as the source of the story and priorities. Check scientific
claims against the full paper, but do not introduce a different story or
copy a source error into the summary. See the abstract and introduction
guidance in [references/story-and-sections.md](references/story-and-sections.md)
for the compression checks.

## Load only the relevant guidance

- For story design, hierarchical outlines, titles, abstracts, introductions, methods, experiments, related work, discussions, conclusions, or paragraph development, read [references/story-and-sections.md](references/story-and-sections.md).
- For theorem statements, mathematical setup, proof sketches, lemmas, appendix proofs, definition order, notation, or cross-reference deferrals, read [references/math-and-proof-writing.md](references/math-and-proof-writing.md).
- For a raw argument that should become one compact theorem with a detailed proof, read both [references/math-and-proof-writing.md](references/math-and-proof-writing.md) and [references/core-theorem-rewrite.md](references/core-theorem-rewrite.md).
- For technical drafting, substantive polishing, paragraph acceptance, first-use terminology checks, stale-definition checks, or corrections that supersede paper content, read [references/review-workflow.md](references/review-workflow.md).
- For sentence-level editing, terminology, equations, figures, captions, citations, source organization, or LaTeX conventions, read [references/style-and-latex.md](references/style-and-latex.md).
- For `simplify`, finding sentences that repeat earlier information, or shortening redundant paper prose, use the [simplify subskill](simplify/SKILL.md).
- For deadline planning, a full-paper audit, submission, anonymization, reproducibility, or an arXiv release, read [references/checklists.md](references/checklists.md).
- To apply the argument patterns of ResNet, Central Flows, River Valley, or Fantastic Pretraining Optimizers, read [references/exemplar-patterns.md](references/exemplar-patterns.md).

## Work from evidence

Inspect the available draft, notes, results, figures, proofs, code, and reviews before writing. Preserve the authors' actual contribution, notation, conventions, and level of certainty.

- Distinguish measured results, observations, derivations, theorems, interpretations, hypotheses, plans, and unknowns.
- Never invent results, citations, assumptions, baselines, numerical values, proof steps, implementation details, or causal explanations.
- Use a visible placeholder or list a gap when evidence is missing. Ask the user only when a missing choice would materially change the paper.
- Do not strengthen a claim for rhetorical effect. Null or contradictory results that affect the central claim remain part of the paper.
- For a method grounded in code, verify how core materials are produced, how information moves between participants, and which capabilities the reported experiments actually use.
- A request to review or explain authorizes findings, not edits. An edit request authorizes only the relevant paper artifacts.

## Respect the exact edit scope

**Unrequested changes to the paper's content are unacceptable.** Preserve the
author's chosen questions, figures, arguments, and section structure outside
the explicitly requested change. A plausible improvement or a consistency
concern does not authorize a broader rewrite.

- Interpret requests such as "use dev40," "redraw the figures," or "update
  Table 1" within the requested comparison. Do not replace a monthly trend
  figure with a cross-model distribution, delete an independent temporal
  audit or test-set description, or rewrite the surrounding interpretation
  without explicit authorization. Preserve each figure's scientific question.
- Before editing, identify the requested content and the directly necessary
  dependencies. Limit linked edits to what the requested change requires,
  such as updating a referenced number or repairing a figure reference.
  Do not use "consistency," "cleanup," or "superseded content" to justify
  deleting unrelated evidence or changing the paper's scope.
- Complete the authorized work. Report other issues and proposed changes
  separately; do not apply them unless the author authorizes them. An outline
  request produces an outline, and an audit request produces findings.
- Before delivery, inspect the actual diff for unrequested deletions,
  replacements, caption changes, and documentation or generator changes that
  would reproduce an unauthorized edit. Report any scope mistake candidly.
- When asked to recover or undo an overreach, restore all affected prose,
  captions, references, figure content, and reproduction instructions, and
  remove unrequested replacement artifacts and generation code. Restoring
  only the visible figure is incomplete. Preserve separately authorized edits
  and other contributors' work; do not perform a blanket repository reset.

## Keep one message per sentence

**Each sentence must communicate one message.** Do not combine independent
findings just because they concern the same model, dataset, or experiment.
Conditions, comparisons, and evidence may support that one message; a second
takeaway belongs in a separate sentence. When the author requests only one
point, retain that point and its necessary context instead of packing the
other findings into subordinate clauses.

For example, a sentence about the additional information needed to pass a
stricter judge should state the average increase and the comparison set.
Do not also report which hint type dominates the original cost or contributes
most to the increase. Those are separate findings.

During revision, identify the single takeaway of each sentence within the
authorized scope. Split sentences with multiple takeaways, or remove an
extra point when the requested edit calls for it. Preserve necessary
scientific qualifications.

## Use stable, literal terminology

Use established technical terms or describe the action directly. Avoid invented jargon and unfamiliar compound labels for ordinary operations. Introduce a new name only when it identifies a genuine recurring concept and the author has adopted it. Apply the same standard to outline headings, paragraph summaries, prose, notation, and figure labels.

### Prefer simple, familiar academic language

**Default to simple, commonly used academic expressions.** Do not make a
sentence sound more technical by choosing longer or less familiar wording
when a standard expression conveys the same claim. Optimize for reader
understanding, not the fewest words: a complete phrase is often clearer than
an undefined shorthand. Preserve distinctions, assumptions, and uncertainty
that matter scientifically.

For example, when the intended meaning and evidence support the replacement:

- Use "no significant correlation" instead of "no detectable monotonic
  association" when reporting a nonsignificant correlation test. Identify the
  test, such as Spearman correlation, where methodological detail is needed.
- Use "47.4 bits under the Directional judge" instead of "47.4 Directional
  bits." State the unit and evaluation condition separately.
- Use "To cover 80% of papers under the Essence judge" instead of "At 80%
  Essence coverage." Make clear what is covered and how success is judged.
- Use "judge" for the evaluator and "criterion" for an acceptance rule;
  do not substitute one for the other.

During revision, check for unnecessarily elaborate phrases and compressed
labels within the authorized scope. Prefer the familiar expression whenever
it preserves the meaning; retain a specialized term when it adds necessary
precision, and explain it at first use.

### Translate code-derived names into paper concepts

**Do not copy nouns or identifiers from code directly into the paper.** Internal
version numbers, implementation codenames, run or cohort aliases, class names,
field names, configuration keys, and repository paths are implementation
evidence, not automatically manuscript terminology. First identify what each
name means scientifically, then use an established term or describe its role in
ordinary language. Apply this rule to author-written prose, headings, captions,
tables, and figure labels, including appendix explanations. Defining an internal
alias or printing it in monospace does not by itself justify retaining it.

Preserve exact strings inside clearly identified verbatim prompts, code listings,
or recorded outputs; do not silently alter quoted evidence or adopt its field
names in the surrounding exposition. Public model, software, and dataset names
needed to identify experimental objects may remain; an internal release tag is
not such a public name. Keep implementation provenance in reproduction records
unless the author explicitly requests it in the manuscript.

When auditing, check a suspicious term's source and reader-facing purpose. Give
the manuscript location, the underlying concept, and a concrete replacement or
reason to retain it. Check rendered figure and table labels as well as prose;
LaTeX labels and asset paths that do not render are not manuscript terminology.

## Plan long drafts before writing prose

For a new draft or substantial rewrite longer than one subsection, first return an English hierarchical outline and wait for explicit approval. The user may waive this gate.

The outline must:

- use one nested numbered list for manuscript content;
- number sections, subsections, paragraphs, and paragraph-development points at the levels relevant to the requested scope;
- restart paragraph numbering within each subsection and development-point numbering within each paragraph;
- give every paragraph one complete-sentence claim or job;
- enumerate beneath it the definitions, reasoning, evidence, qualifications, and transitions it will develop, in reading order;
- show where the main theorem, experiment, figure, example, and limitation enter;
- keep unresolved choices, evidence inventories, and presentation notes outside the manuscript hierarchy.

When revising an outline, return the complete updated hierarchy and preserve stable labels wherever the structure is unchanged, unless the user explicitly requests an excerpt or diff. Treat the approved hierarchy, including every development point, as the drafting contract. Ask before making a material structural departure.

The approval gate does not apply to one subsection or a shorter passage, narrow copyedits, diagnostics, or prose already covered by an approved outline.

## Draft top down

1. Form a compact story spine that connects the problem, tension, central method or theory, mechanism, discriminating predictions, decisive evidence, scope, and significance.
2. Build a claim-evidence ledger. For every important claim, record its scope, supporting theorem or experiment, falsifier or control, main caveat, and draft location.
3. Convert the spine and ledger into the required paragraph-level outline.
4. Draft each paragraph to fulfill its approved job and development points. Establish technical objects before interpreting them, except in a genuine introduction or section overview.
5. Audit the resulting prose against the outline, reader comprehension, terminology order, mathematical or factual correctness, and downstream definition use.

If the desired story conflicts with the evidence, revise the story.

## Make technical prose locally complete

Naming a concept, announcing a theorem, or promising a later explanation does not fulfill a requirement to define, explain, preview, compare, or justify it. Map every paragraph obligation to sentences that actually perform the work.

Technical sections must establish their central objects, operations, assumptions, success events, and measured quantities precisely enough for local reading. Earlier informal familiarity does not replace technical setup.

Outside an introduction or genuine section overview, define an object before commenting on its role, implications, advantages, or restrictions. When a necessary mention precedes its definition, mark it immediately with `(defined later in~\Cref{...})`, point to the location that actually defines it, and provide enough local meaning for the current reasoning. A cross-reference does not itself define a term.

## Audit substantive technical prose

For technical drafting and substantive polishing, follow [references/review-workflow.md](references/review-workflow.md). When independent agents are available, keep outline compliance, prefix-only reader comprehension, and first-use terminology review as distinct checks. Use a downstream stale-definition review when definitions are introduced or reorganized. Reconcile all findings against the same final candidate before accepting the prose.

If independent review is unavailable, perform the same evidence-based checks directly and disclose that independent approval remains unavailable. Never treat a readability pass as evidence of outline compliance or factual correctness.

## Replace corrected material cleanly

Apply this cleanup only to content the author has authorized replacing.
An inconsistency created by an unrequested rewrite does not expand that scope.

When a correction supersedes a claim, theorem, proof, definition, or interpretation, make the corrected version the sole canonical account. Remove stale statements, notation, proof arguments, caveats, examples, captions, comments, and cross-references that depend on the discarded version. Mention revision history only when the user asks for an erratum, change log, reviewer response, or historical comparison.

Search the affected sources for remnants and verify every remaining term, symbol, and reference against the corrected account. Use the superseded-content audit in [references/review-workflow.md](references/review-workflow.md).

## Revise in descending order of leverage

1. Scientific validity and claim accuracy.
2. Story spine and section order.
3. Claim-evidence alignment, controls, uncertainty, and reproducibility.
4. Paragraph logic, definitions, theorem exposition, figures, and captions.
5. Sentence precision, notation, citations, and LaTeX.
6. Formatting and submission checks.

Do not polish text that is likely to be deleted after a structural correction.

## Return a usable result

- For planning, return the story spine, complete hierarchical outline, planned figures or theorems, and separate open decisions.
- For an approved draft or short passage, return publication-ready prose followed only by consequential evidence gaps.
- For revision, provide the revised text or patch first, then summarize substantive changes and claims needing author verification.
- For review, prioritize high-leverage issues and distinguish validity, evidence, exposition, reproducibility, and copyediting.
- Preserve the author's technical voice while removing avoidable complexity.
