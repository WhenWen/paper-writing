# Core theorem rewrite

Use this mode when the user supplies an informal argument, derivation, collection of claims, or rough proof and asks for one clean theorem with a detailed proof.

## Recover the logical content

Identify the exact assumptions, main conclusion, intermediate claims, and dependency order. Do not add assumptions or conclusions merely to make the theorem appear complete.

Use one core theorem when the mathematics genuinely supports that structure:

- State one recognizable main conclusion as concisely as correctness permits.
- Move secondary consequences into the proof, remarks, or corollaries.
- Promote an intermediate claim to a lemma only when it exposes a conceptual step or is reused.
- Place each lemma near its use and make the final proof show how the lemmas combine.
- If the source contains independent results, explain why one theorem would distort them and use the smallest faithful alternative.

## Keep concepts and notation simple

Use standard notation and one symbol per concept. Do not create a symbol merely to shorten a phrase used only a few times. Avoid decorative names for definitions, parameter regimes, and intermediate objects.

Before a symbol enters a calculation or inference, explain it in prose and define it mathematically. Mark necessary advance mentions with the Cref strategy in [math-and-proof-writing.md](math-and-proof-writing.md#cref-strategy). Never make the reader infer a symbol from an equation that already uses it.

## Match proof detail to the audience

Unless the user specifies another audience, write for a third-year undergraduate who knows the standard prerequisites but has not seen the argument.

- Show argument-specific algebraic and logical steps.
- Display substitutions and intermediate equalities when they carry reasoning.
- Name the assumption, lemma, identity, or standard theorem behind each nontrivial step.
- Explain why denominators are nonzero, domains are valid, limits exist, and inequalities have the stated direction when these facts are not immediate.
- After a technical calculation, state what it established and how it advances the proof.
- Do not use “clearly,” “obviously,” or “similarly” in place of a missing argument.

Extra detail should expose logic rather than multiply notation or prose.

## Produce requested deliverables

When the user asks to execute this mode, produce English LaTeX and a compiled PDF unless they request a different deliverable.

- In an existing paper, follow its document class, macros, theorem environments, file organization, and output name.
- For a standalone result, create a minimal source containing only the needed packages, definitions, theorem, lemmas, and proof.
- Compile with the repository's existing build command when available.
- Fix introduced compilation errors, unresolved references, overfull displays, and visible layout problems.
- Return links to the source and PDF.
- If compilation is blocked, return valid LaTeX and name the exact missing package, figure, bibliography, or toolchain.

Write clear English with short declarative sentences and explicit transitions. Avoid semicolons and dash punctuation in the drafted exposition unless mathematical or grammatical correctness requires them.

## Final audit

- The core theorem has one recognizable conclusion.
- Every assumption is used or is explicitly tied to a named lemma.
- Every important intermediate claim is proved before use.
- Every symbol needed for a calculation or inference is explained and defined beforehand, or its necessary advance mention follows the verified Cref strategy.
- No two symbols denote the same object, and no symbol changes meaning.
- The proof reads sequentially without unresolved dependencies.
- The detail matches the intended audience.
- The source compiles, and the PDF matches the source.
