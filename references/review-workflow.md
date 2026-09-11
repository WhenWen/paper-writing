# Technical review workflow

Use this workflow for technical drafting, substantive polishing, paragraph acceptance, definition audits, and corrections that replace existing paper content. It coordinates distinct review questions without letting one favorable verdict hide a failure elsewhere.

## Keep the review questions separate

Evaluate each final candidate along the applicable dimensions:

1. **Outline compliance:** Does the prose fulfill every approved paragraph job and development point at the intended depth and in the intended order?
2. **Reader comprehension:** Can a reader reconstruct the setting, terms, operations, and actual claim from the manuscript available up to this point?
3. **First-use terminology:** Is every paper-specific term, operation, event, quantity, and symbol defined before substantive use or deliberately forward-referenced?
4. **Factual or mathematical correctness:** Are claims, derivations, assumptions, numbers, and implementation descriptions supported by authorized evidence?
5. **Downstream semantic use:** Does each introduced definition have a meaningful later consumer?
6. **Canonical consistency:** After a correction, have all remnants of the superseded account been removed?

A pass on one dimension cannot waive another. Readability does not establish outline compliance, and terminology order does not establish correctness.

## Assign independent review roles

When independent agents are available, keep these roles read-only and isolated:

- The **outline auditor** receives the approved paragraph outline, neighboring paragraph jobs, and candidate prose. It may also perform correctness checks when given the necessary evidence.
- The **reader** receives only the manuscript preceding the paragraph and the candidate paragraph. Do not provide the outline, later text, author explanation, intended interpretation, or another reviewer's verdict.
- The **terminology auditor** receives the same manuscript prefix and candidate paragraph, plus the terminology procedure below. Keep it separate from the reader.
- The **stale-definition auditor** receives the relevant definitions and enough later manuscript, proofs, and appendices to inspect their actual consumers.
- The **superseded-content auditor** receives the corrected canonical account and affected source paths.

For a substantive revision, use fresh isolated readers and terminology auditors. An existing reviewer may recheck a minor wording edit while retaining the same restricted context. Never coach a desired verdict or retry unchanged prose merely to obtain a pass.

If independent agents are unavailable, perform the same checks directly and report that independent approval was unavailable. An audit-only request authorizes findings and proposed repairs, not edits.

## Accept paragraphs against the outline

### Reconstruct the argument of an existing draft

When reviewing flow or substantially restructuring an existing section, first
derive a reverse outline from the prose itself. Record the section's actual
central claim, each paragraph's main claim or job, and the evidence or reasoning
that develops it. Include source locations. Read the whole paragraph rather
than assuming its opening sentence faithfully summarizes its contents.

Check whether each paragraph advances the section's claim and whether its
support establishes its own point. Flag missing logical links, repeated jobs,
unsupported conclusions, and paragraphs whose actual job differs from their
opening. Use this reconstruction to distinguish a wording problem from a
structural or evidence gap.

Then compare the reconstructed argument with the approved outline, when one
exists. Do not fill gaps using author intent or silently treat the reconstruction
as a newly approved plan. Propose material structural changes under the existing
outline approval gate. Skip this extra step for narrow copyedits or when an
equivalent reconstruction already exists for the current candidate.

### Check the approved paragraph obligations

For every drafted or substantively revised paragraph, map each approved job and development point to the sentences that fulfill it. Check:

- purpose and emphasis;
- required definitions, reasoning, evidence, qualifications, and transition;
- the planned progression of points;
- appropriate depth;
- division of work with neighboring paragraphs;
- omissions, unsupported additions, and material that belongs elsewhere.

Topic coverage alone is insufficient. A sentence such as “We define the protocol and prove the theorem below” supplies navigation, not the promised definition or result.

For a preview paragraph, require the actual mechanism or result in words, with enough setting and scope to understand it. Flag duplicated setup, cost definitions, proof machinery, and other detail assigned to later paragraphs. If meeting the approved obligations would overload the paragraph, propose an outline change rather than silently dropping content.

Return sentence-level evidence, necessary repairs, and an explicit verdict. A material departure from the approved outline requires user approval.

## Run an isolated reader check

Ask the reader to reconstruct, as applicable:

- the local setting and participants;
- each technical object and operation;
- available information and the order of interaction;
- the actual claim, comparison, or success event;
- the source of randomness and scope of a probability statement;
- the mechanism or reasoning connecting the premises to the conclusion.

Require exact supporting sentences or an explicit MISSING for each answer. Questions must test comprehension without supplying the intended answers. Later definitions cannot retroactively repair the candidate. A marked forward reference may be acknowledged without reading ahead; the writer or outline auditor must verify its destination separately.

At a technical section boundary, require the central concepts and claim to be re-established locally. Do not excuse missing substance because an introduction mentioned the topic. End with an evidence-backed verdict that names any remaining ambiguity.

## Run a first-use terminology audit

Audit in reading order and stop at the first occurrence of each paper-specific entity, operation, event, quantity, or symbol. Include ordinary-looking words that carry a technical meaning. Treat standard mathematical vocabulary as background only when the intended audience can use it conventionally.

Apply the code-derived naming rule in `SKILL.md` before accepting a term merely
because it has a definition. Check whether it names a scientific concept or
only a repository artifact, distinguish author-written exposition from verbatim
evidence, and propose a reader-facing replacement for unnecessary internal names.

Maintain a ledger containing:

- term or symbol;
- first-use sentence or line;
- exact definition evidence available at that point;
- definition location;
- status;
- unresolved definition dependencies.

Use these statuses:

- **DEFINED HERE**
- **DEFINED EARLIER**
- **STANDARD BACKGROUND**, with a brief reason
- **FORWARD-REFERENCED**, with destination and verification status
- **DEFINED LATER**
- **UNDEFINED**
- **CIRCULAR OR AMBIGUOUS**

An explicit definition states the object's type or role and the meaning needed for its use. An operation says what it acts on and what it does. An event or criterion says what makes it hold. A quantity says what is measured and over which objects. Naming, paraphrasing, or inferring likely meaning from later prose does not define a concept.

Check definition dependencies as well as order. A definition that relies on an undefined specialized concept remains blocked. Outside an introduction or genuine section overview, a comment about an object's role or implications also requires its definition earlier in the technical development.

A first use marked under the Cref strategy is acceptable only when the current passage remains understandable and the referenced destination is verified. Otherwise, technical prose fails this audit when a concept required by the current claim is DEFINED LATER, UNDEFINED, or CIRCULAR OR AMBIGUOUS.

For every blocker, propose the smallest repair that preserves the author's meaning: define the object before naming it, move an existing definition earlier, or replace an unnecessary term with an established expression. Do not invent a definition or hidden assumption. Recheck introduced terms and affected dependencies after repair.

## Run a stale-definition audit

A stale definition introduces a named concept or symbol with no meaningful use after its definition and immediate explanation. Occurrence counts are insufficient because the same word can have another meaning, while a concept can be used through a symbol, alias, or defining property.

Maintain a semantic-use ledger with:

- exact meaning and definition location;
- intended scope;
- later candidate uses with locations and quotations;
- whether each occurrence invokes the defined meaning;
- the claim, operation, proof, or downstream definition that depends on it.

Use the verdicts:

- **USED** when a specific later argument depends on the concept;
- **STALE** after the relevant downstream scope has been checked and no dependency exists;
- **PLANNED** when an unfinished outline names a specific future consumer;
- **UNRESOLVED** when later scope or meaning has not been inspected.

Immediate restatements, decorative name checks, circular chains of unused definitions, and unrelated occurrences in prompts, code, or quotations do not establish use. Trace symbols, aliases, defining properties, and appendix dependencies before declaring a definition stale.

For a stale definition, remove the name, retain essential content in ordinary language, or introduce it at first substantive use. Do not add artificial uses merely to preserve terminology. Before removal, verify that no assumption changes and no reference or dependent definition becomes dangling.

## Audit superseded content

When a correction replaces paper content, give the auditor the corrected canonical claim and affected sources. Search for stale:

- factual statements and interpretations;
- theorem statements, assumptions, and proof arguments;
- definitions, notation, and terminology;
- caveats and examples;
- captions, comments, and cross-references.

Reconcile every finding and recheck downstream dependencies after removal. Do not preserve revision history inside the paper unless the user requested an erratum, change log, reviewer response, or historical comparison.

## Complete the acceptance loop

1. Draft the paragraph or correction from authorized evidence.
2. Run all applicable reviews against that candidate.
3. Reconcile findings without weakening the approved outline or claim accuracy.
4. Obtain author direction if a repair requires a new assumption or material outline change.
5. Re-run affected reviews on the final candidate.
6. Accept the prose only when the same final candidate has evidence-backed passes on every applicable dimension.

A minor edit needs only the checks it can affect. A substantive change invalidates earlier passes.
