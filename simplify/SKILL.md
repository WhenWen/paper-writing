---
name: simplify
description: Find and shorten research-paper sentences whose information is already supplied by earlier sentences. Use for semantic redundancy audits or requests to simplify a paper by deleting or merging repeated information; preserve definitions, evidence, and necessary local restatement.
---

# Simplify

Read the paper in manuscript order and identify later sentences that add little
or no information beyond earlier sentences. Propose deletion, merging, or a
shorter sentence that retains the new information. This is an information-level
review, not merely a search for repeated words or a general style rewrite.

## Establish the scope

Use the current manuscript and its include order. Ignore old drafts, scratch
copies, and unreferenced source files. Review the requested scope; for a whole
paper, cover the abstract, main text, captions, and author-written appendix
prose, and report any portions not reviewed.

When the user asks to find examples or review opportunities, return concrete
suggestions without editing the paper. When the user asks to apply simplification,
make the supported edits within that scope. Existing authorization applies; do
not add a separate approval gate.

## Compare information in reading order

1. Track what earlier retained text establishes: the claim, objects, conditions,
   evidence, scope, and purpose. For a suspected redundant sentence, identify
   the exact earlier sentence or sentences that cover its information.
2. Separate the candidate's repeated content from its new contribution. A new
   number, condition, operational detail, implication, qualification, or necessary
   transition may justify retaining part or all of it. Shared subject matter or
   similar vocabulary is not evidence of redundancy.
3. Prefer deleting a sentence that only restates its immediate context. For a
   mixed sentence, remove the repeated clause and preserve the new information.
   Merge sentences when that preserves their logical progression more clearly.
   Do not replace repetition with an empty summary or an unnecessary new term.
4. Read the edited paragraph in context. Check grammar, antecedents, logical
   connections, first-use definitions, assumptions, citations, and downstream
   references. A shorter passage must still perform the paragraph's job.
5. Check proposed edits together. Every earlier statement used to justify a
   deletion must survive the combined edits, or be preserved in the replacement.
   Do not count overlapping alternatives as independent savings.

## Preserve useful repetition

Judge repetition by its role and distance, not occurrence count. An abstract
and introduction may summarize the same result; a caption, theorem statement,
or section opening may need to stand on its own. An intuitive preview does not
replace a later precise definition, and stating a theorem does not replace its
proof. A result and its interpretation are different information when the latter
adds a supported implication.

Keep the premises, scope, uncertainty, and qualifications that make a claim true.
Do not remove them merely because they appeared elsewhere. Do not move essential
explanations out of the reader's local context to save words.

Treat verbatim prompts, model outputs, quotations, and reproduction material as
evidence rather than ordinary prose to rewrite. Independent prompts may need the
same instructions. Preserve user-requested examples and comparisons. If excerpting
quoted evidence is within the requested scope, mark omissions and preserve the
meaning and stated provenance.

## Return reviewable examples

Use a numbered list, ranked by confidence and useful reduction. For each finding:

1. Locate and quote the earlier text that already supplies the information.
2. Locate and quote the later sentence, distinguishing any novel part.
3. Give an exact proposed replacement, or explicitly recommend deletion.
4. Explain why the cut preserves meaning and local readability; flag a genuine
   tradeoff rather than presenting an uncertain cut as safe.

Use source file and line links when available. Word savings are optional; if
reported, state the counting convention, count actual before/after text, and
separate proposed savings from applied savings. Do not claim a page reduction
without compiling and checking it.

Report a few useful repetitions that were deliberately retained when they clarify
the boundary. Return only supported findings rather than filling a quota. For
applied edits, verify the affected prose, references, and rendered layout as
appropriate, and summarize both the edits and any unresolved candidates.
