# Technical style and LaTeX

Apply these conventions when they do not conflict with the venue template or the repository's established style.

## Prose guardrails

Unless required by mathematical notation, LaTeX syntax, a quotation, or a user-specified title, avoid the contrastive construction `not ... but ...` and avoid colons in outlines and paper prose. Prefer direct affirmative statements, periods, commas, or separate sentences.

## Sentence and paragraph style

- Put the paragraph's main point first and give the paragraph one primary job. In technical setup, establish the object before commenting on it; overview and introduction previews are the exception.
- Describe a phenomenon with the shortest sentence that remains accurate. State what happened before explaining why it happened.
- Prefer concrete subjects and verbs: “The bound scales with $d$” is clearer than “A dependence on $d$ can be observed.”
- Use the same precise term for the same concept. Do not rotate synonyms for variety when readers may infer a technical distinction.
- Keep formulas grammatically integrated into sentences. Add punctuation after displayed equations.
- Avoid beginning a sentence with a symbol when a short noun phrase would orient the reader.
- Avoid contractions and unexplained colloquialisms in formal prose.
- Use hyphens in compound modifiers: “$(d-k)$-dimensional,” “real-world data,” and “ground-truth label,” but “the ground truth.”
- Use the Oxford comma consistently.
- Check articles, singular/plural agreement, and subject--verb agreement, especially in long sentences around citations.
- Break a long sentence when it carries multiple logical relationships. Short does not mean choppy: preserve explicit transitions.

For a phenomenon sentence about an already established object, prefer the structure “object + change or relation.” Put further mechanism, evidence, and caveats in later sentences unless a qualifier is required to make the first sentence true. Do not optimize for raw word count at the expense of scope, uncertainty, or mathematical correctness.

When introducing a difficult idea, choose the order that minimizes reader effort. A concrete example may define the object before symbolic formalism. Place interpretive comments after the relevant definition; introductions and section overviews may preview the idea earlier.

## Terminology and macros

Use standard terminology or a direct description of the action. Avoid coining
labels for ordinary operations or compressing them into unfamiliar compound
phrases. For example, describe the Generator as asking the Oracle to select a
research field from a taxonomy and a contribution category, rather than naming
this operation "priced taxonomy choices." Explain the cost separately where
it is needed. Apply the same rule to outline headings and paragraph summaries.

Keep the paper's established or user-adopted terms consistent. Maintain a
terminology sheet if several authors are editing. Use semantic LaTeX macros for:

- method and dataset names;
- mathematical objects or operators;
- notation likely to change;
- repeated formatting distinctions.

Do not hide ordinary prose behind macros. A macro should improve consistency or maintainability.

## Equations

- Keep a displayed equation on one line when it fits comfortably at the normal
  manuscript font size, with room for its equation number. Short chains of
  equalities or inequalities usually belong in a single `equation` environment;
  do not insert line breaks solely because another relation begins.
- Use `align`, `aligned`, or `split` when width requires it or separate lines
  clarify a substantive derivation. Align at the logical relation. Preserve
  readable spacing and notation rather than shrinking fonts or squeezing a
  long equation onto one line. Verify the final width in the compiled paper.
- Label equations or individual lines that will be referenced. Suppress numbering only for lines that have no later identity.
- When a line uses a theorem or transformation that is not obvious, put a short explanation close to that line. A compact annotation is better than forcing the reader to match “line 3” with a later paragraph.
- Avoid `$$...$$`; it does not integrate well with document numbering and spacing.
- Define important quantities before displaying an equation that depends on them. A trailing “where” clause is fine for secondary or familiar symbols.
- Use `\mathrm{}` or `\operatorname{}` for named operators and semantic macros for recurring special quantities.
- Prefer explicit delimiter sizing such as `\bigl` and `\bigr` when automatic `\left` and `\right` produces distracting sizes.
- Use words for trivial pseudocode operations when symbols make them harder to parse, for example “add $a$ to $S$.”

## Theorem and equation numbering

For theorem-heavy papers, a shared counter for theorems, lemmas, propositions, and corollaries often reduces ambiguity. Number statements and equations by section when the venue and existing source permit it. Definitions may use the same counter unless a separate sequence clearly helps.

Every theorem, lemma, and claim should have a proof immediately afterward or a precise pointer to its proof. Use a `proof` environment; when the statement is not adjacent, name it in the optional proof heading.

## Figures and captions

Treat each figure as one idea.

- Begin the caption with a bold or otherwise visually clear takeaway sentence when the template allows.
- Explain panels, colors, axes, metrics, units, and comparison conditions.
- State what the reader should conclude, while distinguishing observation from interpretation.
- Make the caption self-contained enough for an expert skimming only figures.
- Use the same axis limits for directly comparable plots unless a different scale is necessary and clearly marked.
- Choose convenient units such as thousands or millions instead of long strings of zeros.
- Check font, legend, label, and line sizes at the figure's final paper dimensions.
- In the compiled PDF, all figure text (including ticks, legends, annotations,
  and numerical values) must be at least as large as normal body text, and
  figure/panel titles must be larger. Verify size after inclusion scaling;
  change the layout rather than shrinking text below that floor.

For a mechanism or protocol figure, prefer a concrete, traceable instance when
it makes the interaction easier to understand. Show the relevant input or
current state, actual questions or alternatives, selection probabilities when
applicable, and the selected path or resulting update. Plan this example with
the outline so the figure and prose explain the same operation. Preserve real
labels and structural relationships when illustrating a taxonomy or other
experimental resource, and label simplified answer sets or hypothetical
probabilities as illustrative. Choose the panel arrangement for the reader's
task rather than prescribing one layout for every paper.

Plot trends when the trend is the message; use tables when exact values or many categorical comparisons matter.

### Main-text figure page fit

Treat the figure and its caption as one layout unit. A main-text figure that
occupies a whole page or is isolated on a float-only page requires another
layout pass, even if its standalone export looks good. Always try to reduce
the figure height, caption length, or both so the unit can share a page with
meaningful body text.

- First remove excess plot margins and inter-panel spacing. Try a shorter
  aspect ratio, a more compact panel arrangement, and concise labels or legends.
  Moderate scaling is acceptable when the final-size text remains readable.
- Shorten captions by removing repeated results and explanations already clear
  from the panels. Retain the central takeaway, essential panel definitions,
  metric and sample information, and qualifications needed to interpret the
  result correctly. Put extended discussion in the surrounding prose.
- Check whether unnecessary forced page breaks or float barriers are causing
  the isolated page. Adjust local placement where appropriate without changing
  venue margins, global typography, or hiding overflow with negative spacing.
- Recompile and inspect the figure page and its neighbors after each meaningful
  adjustment. A successful build or an attractive standalone PNG does not
  establish that the paper layout fits.

Do not accept a full-page main-text figure as the default solution to crowded
labels. If reasonable compaction attempts cannot preserve readability and
essential content, flag the unresolved layout and ask whether to simplify the
figure, relocate supporting panels, or explicitly allow a full-page exception.

## Tables

Give each table one main comparison or question. Make it interpretable without
requiring readers to guess the metric, setting, or meaning of a row.

- Put metric direction in headers when it is not obvious, such as accuracy
  $\uparrow$ or error $\downarrow$, and state units and any scaling factors.
- Use consistent numeric precision within each metric column, appropriate to
  the measurement uncertainty. Align numbers consistently, preferably by the
  decimal point, and align descriptive text to the left.
- Prefer sparse `booktabs` rules over vertical separators, double rules, or
  a horizontal line after every row. Group related settings with clear headers
  and partial rules where helpful. Follow the venue's required table style.
- Name ablation rows or provide attribute columns so readers can identify what
  was removed, replaced, or held fixed. Define symbols and abbreviations.
- Use restrained emphasis for key comparisons and explain its meaning. Avoid
  implying that a tiny numerical lead establishes a meaningful improvement.
- Give table captions the same care as figure captions. State the setting,
  essential protocol, notation, and uncertainty convention when applicable.
  Prefer a caption above the table unless the venue specifies otherwise, and
  put the LaTeX label after the caption.
- Check the table at final paper size. Preserve readable text and explicit
  comparisons when simplifying a wide table or splitting it into groups.

## Citations

With `natbib`, use `\citep{}` for parenthetical citations and `\citet{}` when the citation is grammatically part of the sentence. Removing a `\citep{}` should leave a valid sentence; removing a `\citet{}` generally should not.

Maintain grammatical agreement. “Smith et al. show” refers to authors; “the work of Smith et al. shows” refers to a work. When discussing a limitation, target the exact result or assumption: “Theorem 2 requires X” is more precise and collegial than a broad claim about the authors.

Verify bibliographic data against the published version when available. Do not invent citation keys or references. Preserve existing keys unless there is a strong repository reason to change them.

## Source organization

For a multi-section LaTeX paper, prefer a small main entry point—commonly `main.tex`—that loads a shared macro/style file and inputs one source file per substantial section. Follow the current repository if it already uses another organization.

Avoid large regions disabled with `\iffalse...\fi`; version control and small comments are easier to edit and review. Preserve unresolved coauthor comments unless the user explicitly asks to remove them. Resolve only comments that are clearly addressed, and do not erase uncertainty that still needs author review.
