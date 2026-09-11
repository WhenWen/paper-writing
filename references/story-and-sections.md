# Story and section design

## Start with a reader contract

Before drafting, write down:

- **Problem:** What specific question or task does the paper address?
- **Stakes:** Why should this audience care now?
- **Tension:** What observation, limitation, contradiction, or decision makes the problem nontrivial?
- **Central idea:** What is the one method, model, reformulation, or principle the reader should remember?
- **Mechanism:** Why should that idea work?
- **Evidence:** Which theorem, experiment, or comparison most directly supports it?
- **Boundary:** Where does the claim stop?

If any answer requires “and” several times, the paper may contain multiple stories. Choose a primary one and make secondary contributions support it.

## Convert the story into a claim--evidence outline

Use a hierarchical outline before full prose. Each node should be a claim or communicative job, not merely a topic.

Weak outline item:

> 4.2 Learning-rate experiments

Stronger outline item:

> 4.2 Larger learning rates improve long-horizon progress by moving the trajectory into flatter regions

For every major claim, record:

- the evidence that supports it;
- the alternative explanation or confound that must be ruled out;
- the figure, table, theorem, or example that carries the evidence;
- the precise scope of the conclusion.

Missing evidence discovered during outlining is a research task, not a prose problem.

Choose section boundaries by the questions the reader needs answered. Merge or
split inherited sections when their assigned jobs warrant it. A trajectory that
explains how a method runs belongs with the method or experiment instantiation
as a walkthrough. A comparison that tests the effect of a design choice serves
as an ablation. A single illustrative trajectory supports explanation; broader
performance claims require appropriate experimental evidence.

## Outline paragraphs before writing them

For every outline revision, including a change to a single phrase, output the
complete current hierarchy for the outline under discussion. Include unchanged
parts and carry forward all accepted revisions. Do not require the user to
combine an excerpt with earlier responses to reconstruct the current outline.
Only limit the output to an excerpt or diff when the user explicitly requests
that format. Keep presentation notes and unresolved issues outside the outline.

Render the outline as one hierarchical numbered list, with ordered-list
markers at every level and a reference label for every manuscript-content
item. Restart paragraph numbering at 1 under each subsection, and restart
development-point numbering at 1 under each paragraph. Thus the first paragraph
in the second subsection is `2.1`, even when the first subsection has four
paragraphs. Preserve manuscript section numbers when included, and use compound
labels such as `4.2.1.3` when needed to make a nested point unambiguous.
Keep labels stable across revisions
when the structure is unchanged. Nest subsections under sections,
paragraphs under their section or subsection, and development points under
each paragraph. Omit levels outside the requested scope. Each paragraph item
states its single main claim or job as a complete, direct sentence. Its child
items state the successive points that paragraph will explain, in reading
order, with enough substance to review the argument before prose is written.
Separate the actual setup, definitions, reasoning, evidence, qualifications,
and transition where applicable; do not impose a fixed number of points or
require every paragraph to perform all these jobs. Each child item is a
point within the paragraph, not a new paragraph or necessarily one sentence.

For example, a method-section outline can contain the following structure.

4. **Section 4** explains how the agents implement the protocol.
   1. **4.1** explains bid construction.
      1. **4.1.1** defines the Generator's visible state.
         1. **4.1.1.1** Identify the public resources and previously selected answers available to the Generator.
         2. **4.1.1.2** Distinguish confirmed facts from the Generator's working hypotheses.
         3. **4.1.1.3** Explain how these inputs determine the context used to construct the next question.
      2. **4.1.2** explains how a bid commits the available answers and their probabilities.
         1. **4.1.2.1** Specify the finite answer set and its normalized probability distribution.
         2. **4.1.2.2** State that both are fixed before the Oracle selects an answer.
         3. **4.1.2.3** Explain how the selected answer updates the visible state for the next step.
   2. **4.2** explains Oracle guidance.
      1. **4.2.1** defines the Oracle's available information.
         1. **4.2.1.1** Identify the target information held privately by the Oracle.
         2. **4.2.1.2** Specify the displayed questions and choices it can inspect.

Read the paragraph-level items alone to check the overall argument, then
read each paragraph's child items to check its internal progression. A
paragraph summary with several sentences does not replace the nested list of
its development points. Keep unresolved choices, missing evidence, and
presentation notes outside this manuscript outline.

Then expand each paragraph-level item and its children into one paragraph:

- use the item, or a refined version of it, as the opening sentence, with definition/setup paragraphs establishing their objects before interpreting them;
- add only evidence, explanation, qualification, or transition that serves that point;
- develop every approved child item in its planned order, integrating adjacent points into sentences as appropriate;
- split the paragraph when a second point could stand as its own item;
- delete the paragraph when its item does not advance the section's argument.

This intermediate outline keeps sentence polishing from hiding a structural problem.

## Titles

Prefer a short title with a distinctive phrase that identifies the object and contribution. Avoid titles so broad that they could describe an entire field. A subtitle can pair a memorable concept with a precise setting.

Check that the title does not overclaim beyond the strongest result.

## Abstract

Compress the introduction by importance, rather than shortening every
paragraph equally. First identify its central question, proposed idea,
essential mechanism, decisive evidence, and main implication. Retain the
elements needed to reconstruct that story; select only the most informative
numbers and omit secondary ablations or implementation details. Check each
abstract claim against the introduction and its evidence in the full paper.
An omission must not broaden a claim or turn a conditional implication into
an established result.

Write one self-contained paragraph. A reliable sequence is:

1. setting and stakes;
2. specific tension or gap;
3. proposed concept, method, theory, or protocol;
4. mechanism or scope;
5. decisive theoretical or empirical evidence;
6. main quantitative result when it matters;
7. significance or limitation.

Do not turn the abstract into a table of contents. Include the results that change the reader's belief, not every result in the paper. Expand acronyms only when they recur or are central.

Choose an abstract pattern that fits the contribution rather than forcing every
paper into the same sequence:

- **Challenge to contribution.** State the obstacle, the contribution that
  addresses it, its supported benefit, and the decisive evidence.
- **Challenge to insight to implementation.** When the conceptual insight is
  distinct from its implementation, explain the insight in plain language
  before naming the method that realizes it. Then state the supported benefit
  and evidence. A method name alone does not explain the insight.
- **Several contributions with their benefits.** When several contributions
  are essential to the same story, pair each with its specific supported benefit
  before giving the overall evidence. Avoid a list of unexplained components.

These are optional patterns. Match evidence to the claim, including theoretical
results where appropriate, and retain qualifications needed for accuracy.

## Introduction

Compress the full paper into a coherent account of its most important
contributions. Use the methods, theory, experiments, and discussion to decide
what deserves emphasis. Preserve the main reasoning and decisive evidence,
while leaving proofs, detailed protocols, and secondary findings to the body.
A reader should understand the paper's contribution and its limits without
reading every section. Check that the abstract preserves this same emphasis
at a smaller scale.

A strong introduction often makes these moves:

1. **Setting:** define the object and why it matters.
2. **Tension:** show the concrete failure, anomaly, practical constraint, or unreliable convention.
3. **Question:** state the question in a form the paper will answer.
4. **Idea:** name the conceptual move and contrast it with the standard picture.
5. **Mechanism:** explain the idea using a running example, decomposition, construction, or cartoon.
6. **Contributions and evidence:** state results as claims, with enough numbers or theorem content to be meaningful.
7. **Scope:** say what the paper does not yet explain or test when that boundary prevents misreading.

Place an opening figure early when the central idea is visual. It should function as a graphical abstract: the caption states the main takeaway, explains encodings, and connects panels into an argument.

Avoid beginning with a broad history of the field. Cite directly relevant work while creating the tension; defer a fuller conceptual comparison to related work.

Describe the contribution's relationship to prior work accurately, including
when it is incremental. A baseline followed by a well-motivated improvement can
be the clearest explanation. Do not hide that relationship or inflate novelty
to make the work appear less incremental. Explain what the change establishes
and why that result matters.

## Method or model section

Open with the section's question and a substantive preview of its setup and
central mechanism or result. Add a roadmap if the section is long. Rebuild the
technical setup locally even when the introduction already gives its informal
motivation. A useful order is:

1. motivating example or failure of the baseline;
2. intuitive description of the method or model;
3. formal definition;
4. important design choices and why they are necessary;
5. implementation or computational implications;
6. predictions, invariants, or comparisons the method creates.

Define the simplest core case first, then generalize. Separate the essential idea from engineering choices. If the method is a reformulation, show the original and new forms side by side and explain what becomes easier.

### Describe an implemented method

For each important component, check three questions while outlining:

- **Purpose.** What concrete problem or requirement motivates this component?
- **Operation.** What are its inputs, relevant structures, ordered steps, and
  outputs, and how do those outputs enter the rest of the method?
- **Justification.** Why should the design address the problem, and what proof,
  controlled comparison, or other evidence supports the claimed benefit?

Distinguish design rationale from an established mechanism or measured gain.
If justification is only a hypothesis, label it accordingly. These questions
are a coverage check, not a required three-paragraph template or an assumption
that every component is novel. Establish the component before discussing its
advantages, following the definition-order rules.

When writing from a codebase, check the following relationships while building
the paragraph outline, before polishing its wording.

1. **Explain the origin of core materials.** When first introducing a target,
   reference summary, taxonomy, or other derived material needed to understand
   the method, state its source, generation or filtering procedure, and the
   responsible model or process. Specify access restrictions when they matter
   to the protocol. Replace vague phrases such as "fixed collection rules"
   with the actual source and selection procedure. Keep exhaustive generation
   settings in the reproducibility details when they would interrupt the setup.
2. **Explain operations before selection among operations.** Define available
   strategies or actions before a controller's decision among them. State the
   unit of interaction, who acts at each step, which questions, options, or
   probabilities are prepared before selection, and what happens afterward.
   Renaming an unexplained implementation term does not supply this sequence.
3. **Distinguish state, context, and transmission.** Check separately what each
   participant maintains, what it uses to construct its next action, and what
   is actually sent to another participant. Maintaining a fact list does not
   imply transmitting the complete list; separate state objects should remain
   separate in the account. Use a readable abstraction that preserves the
   implementation's information boundaries. Treat a proposed change to the
   implementation as a proposal until it is implemented and verified.
4. **Select details by their experimental role.** Include details that determine
   the task, information flow, cost, success criterion, or interpretation of
   the reported results. Additional implementation capabilities and routine
   caching details can move to an appendix or be omitted when they have no such
   role. Clearly scope any retained documentation of unused capabilities.

## Experiments

Every experiment should answer a question. Organize subsections by questions or claims, not by the order in which runs were performed.

For each experiment, state:

1. **Question or hypothesis.** What uncertainty does this experiment resolve?
2. **Discriminating design.** Why can this comparison answer the question? Name matched factors, controls, and possible confounds.
3. **Setup.** Give the information needed to interpret the result; move exhaustive reproducibility details to an appendix when appropriate.
4. **Result.** Lead with the observed pattern and the relevant magnitude or uncertainty.
5. **Interpretation.** State exactly what the result supports and what it does not establish.
6. **Failure or robustness.** Probe scale, dataset, seed, hyperparameter, ablation, or boundary when it is relevant to the claim.

Use tables when exact values or many categorical comparisons matter. Use plots when trend, variation, scaling, or trajectory is the message. Do not use a large result table as a substitute for a stated question.

For benchmarks, define fairness operationally: tuning budget, search space, compute accounting, data order, evaluation point, model scale, and uncertainty. A negative result is persuasive only when the protocol gives competing methods a credible chance.

## Related work

Organize related work by the conceptual axes needed to locate the contribution. For each closest line of work, say:

- what object or setting it studies;
- what result or mechanism it establishes;
- the exact dimension on which the present paper differs.

Be specific and neutral. Prefer “Theorem 2 assumes X, whereas our result handles Y” to “prior work is unrealistic.” Do not imply that absence from the bibliography means absence from the literature; verify citations before making novelty claims.

## Discussion and conclusion

Use discussion to answer “How should the reader now think differently?” Connect the result to a broader principle without outrunning the evidence. Explain meaningful limitations as boundaries on the model, method, or evaluation—not as ceremonial caveats.

The conclusion should answer the introduction's question, restate the changed mental model, and identify the most consequential boundary or future direction. Do not merely repeat the abstract sentence by sentence.

## Paragraph test

Before drafting, translate each paragraph's assigned job into questions a
reader should be able to answer after reading it. Test the expanded prose
against those questions, with sentence-level evidence for every answer.

- A definition identifies the object and its meaning or operational criterion.
- A method or protocol preview explains who or what acts, what information or
  inputs are available, and how the central interaction or transformation works.
- A result preview states what is established, for which objects or quantities,
  and under what scope. A probability claim identifies the event and the source
  of randomness; a comparison identifies the compared objects and relationship.
- An explanation or justification supplies the mechanism, reasoning, or evidence
  connecting its premises to its conclusion.

A sentence such as "We define the protocol and prove the theorem below" supplies
navigation only. It contributes no evidence that the protocol or theorem has
been explained. Do not replace these content obligations with checks for topic
coverage, familiar vocabulary, or fluent prose. If meeting the obligations would
overload a paragraph, propose a split or outline adjustment under the approval
gate instead of silently omitting the substance.

Also ask:

- What single job does it perform?
- Does the first sentence begin performing that job, rather than merely announce it?
- Does each later sentence develop, support, qualify, or transition from it?
- Would the paper still make sense to an expert reading only paragraph openings?
- Is the transition to the next paragraph causal or logical rather than merely topical?

If a paragraph has two equally important points, split it. If its point appears only at the end, move the point forward when its required definitions are already available. In technical setup, establish the object before giving remarks about it.

### Comment-order check

Reader and outline audits must distinguish definitions from comments about
their purpose, implications, advantages, or restrictions. For each such comment,
identify its referent and quote the preceding definition that makes the comment
understandable. In technical setup, flag a comment that precedes the relevant
definition even if its words are familiar or the introduction mentioned them.
Move it after the definition that supports it.

An introduction or genuine section overview may preview the meaning or role
of an object before the full definition. The outline auditor must justify this
exception from the paragraph's actual job, rather than its position as a first
sentence. Prefix-only readers assess the available text without reading ahead.
A Cref pointer does not turn a premature technical remark into a definition.

### Independent paragraph acceptance

Use [review-workflow.md](review-workflow.md) to coordinate outline compliance, isolated reader comprehension, first-use terminology, factual or mathematical correctness, and downstream definition use. Keep the paragraph test above as the substantive acceptance standard; the review workflow defines reviewer isolation, evidence requirements, rechecks, and fallbacks.
