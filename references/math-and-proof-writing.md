# Mathematical results and proofs

## Core theorem rewrite mode

When the user asks to turn an existing argument into one core theorem and proof, also read [core-theorem-rewrite.md](core-theorem-rewrite.md). This is a specialized restructuring mode. Do not impose it on a paper with several genuinely independent results.

## Present the main result as soon as it is appreciable

“As soon as possible” is subordinate to “understandable and worth caring about.” Before the main theorem, give only the material required to appreciate it:

1. the question and why the theorem resolves it;
2. the minimum setting and notation;
3. intuition for the object or algorithm being studied;
4. assumptions, including why nonstandard assumptions are meaningful;
5. a simple example or special case when it makes the statement legible.

Do not make the reader cross several pages of machinery before learning the result, but do not display an opaque theorem merely to place it early.

## Main-result sequence

A reliable main-result subsection contains:

1. **Motivation and message.** One or two sentences recalling the problem and the expected takeaway.
2. **Setup.** Definitions and notation needed locally.
3. **Assumptions.** State their scope explicitly. Explain realism, relation to prior assumptions, and which are technical.
4. **Theorem.** Make quantifiers, dependencies, probability statements, and regimes unambiguous.
5. **Interpretation.** Explain the conclusion, parameter dependencies, simplified cases, comparison with prior results, and important subtleties.
6. **Proof pointer.** Say whether the proof is immediate, follows next, or appears in a named appendix section.
7. **Proof overview.** Include one when the proof contains a reusable conceptual plan or would otherwise feel like a black box.

The prose after the theorem is part of the result. A technically correct theorem that readers cannot interpret is not yet well presented.

## Treat statements as typed interfaces

Design each theorem, lemma, and proposition like a readable function:

- **Inputs:** ambient setting, assumptions, definitions, parameter regimes.
- **Outputs:** conclusion, probability, approximation, rate, or invariant.
- **Scope:** which prior assumptions are inherited and from where.

Avoid long chains such as “in the setting of Lemma j-1” that force the reader to reconstruct assumptions recursively. “In the setting of Theorem 3.1” is useful only when the inheritance structure is shallow and clear.

State helper lemmas at the most interpretable useful level. If a matrix lemma holds for arbitrary positive-definite matrices, state it that way rather than baking in the paper's later special substitution—unless the abstraction would make the lemma harder to understand and it is not reused.

## Build a proof skeleton

For a long proof, restate the main theorem near its appendix proof using a shared macro or restatable environment so the statement cannot drift.

Before detailed proofs, give a skeleton:

- name the key intermediate claims in their logical order;
- state what each claim means conceptually;
- explain how their conclusions compose into the theorem;
- identify the one or two genuinely difficult steps.

The skeleton may suppress technical constants, but it must not create a false argument. If it is informal, include a short formal assembly proof that links the lemmas with the exact assumptions.

Good lemmas correspond to conceptual or reusable steps that an expert could plausibly believe before reading the proof. The list of lemma statements and surrounding prose should reveal the proof plan.

Prefer a proof tree two or three levels deep. To flatten a deep tree:

- let parallel lemmas depend sequentially when natural;
- extract genuinely shared arguments into one proposition;
- prove local propositions near the lemma that uses them;
- reserve a later helper section for broadly reusable technical facts, and restate the invoked conclusion when citing forward.

Avoid repeated “similarly to Lemma 1” arguments when a shared proposition would expose the common structure.

## Order and locality

Allow sequential reading whenever practical. State a claim before relying on it. If a modular helper appears later, do more than cite its number: summarize the exact conclusion being invoked.

Recall a definition or symbol that has not appeared recently. Write “the river projection $P(w)$” rather than bare “$P(w)$” when the reminder prevents a lookup. Local redundancy is cheaper than forcing a reader to search several pages backward.

## Cref strategy

For a necessary reference to a concept whose definition appears later, place
`(defined later in~\Cref{...})` directly after the relevant term.
Use the label of the section, theorem, or definition containing the actual
definition. A vague "defined below" or a link to a mere mention is insufficient.
If only the formal details come later and the concept has already been
explained, use "formally defined later" to describe the destination accurately.

Verify that the destination occurs later, contains the promised definition,
and has a valid label. When editing LaTeX, ensure `\Cref` is supported by the
manuscript setup and the reference resolves in the compiled paper. A planned
destination in an unfinished outline remains an unresolved verification item
until it is written and checked.

The pointer permits an explicitly deferred mention. It cannot supply the
meaning of a quantity being calculated or an operation being used in the
current argument. Give enough local explanation for the current claim, or
move the necessary definition earlier. Do not introduce the full later
construction merely to support a brief scope qualification.

Prefix-only reader and terminology agents must keep their restricted context.
They may recognize a marked deferral without reading ahead, while the writer
or outline auditor verifies the destination separately. Acceptance requires
both a locally understandable passage and a checked destination.

## Notation checks

- Define every paper-specific technical term and symbol at first substantive use. Mark necessary deferred mentions using the Cref strategy. Use one name or symbol for one concept.
- Distinguish discrete indices, continuous time, random variables, events, vectors, matrices, and operators consistently.
- State norms, probability spaces, conditioning, and asymptotic regimes.
- Use semantic macros for notation likely to change or recur.
- Use established operator forms such as `\operatorname{tr}`, `\argmax`, and `\lVert\cdot\rVert` rather than ad hoc italics.
- Number equations and statements that are cited later. Use section-based numbering when consistent with the document.
- Punctuate displayed equations as parts of sentences.
- Apply the single-line display preference and width checks in
  [style-and-latex.md](style-and-latex.md#equations).

## Terminology and definition audits

Use [review-workflow.md](review-workflow.md) for the first-use terminology ledger, definition-dependency checks, stale-definition audit, reviewer isolation, and acceptance loop. This reference defines the mathematical and cross-reference rules that those audits enforce.

## Proof-exposition audit

An expert reading only the theorem statements, lemma statements, and adjacent prose should understand the proof strategy. Check:

- Are all assumptions visible without tracing a long inheritance chain?
- Does every lemma have a conceptual reason to exist?
- Is each lemma used soon after it is introduced, or is its later role signposted?
- Are parameter dependencies interpreted rather than merely displayed?
- Are special cases used to make the theorem appreciable?
- Does every deferred proof have an accurate pointer?
- Does every appendix proof use a proof environment and identify the statement being proved?
