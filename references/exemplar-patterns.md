# Patterns from the exemplar papers

This reference distills writing patterns from four papers selected by the user. It is a synthesis, not a requirement to imitate their surface style.

## Sources

- He et al., *Deep Residual Learning for Image Recognition* (ResNet), arXiv:1512.03385.
- Cohen et al., *Understanding Optimization in Deep Learning with Central Flows*, arXiv:2410.24206.
- Wen et al., *Understanding Warmup-Stable-Decay Learning Rates: A River Valley Loss Landscape Perspective*, arXiv:2410.05192.
- Wen et al., *Fantastic Pretraining Optimizers and Where to Find Them*, arXiv:2509.02046.

## The common deep structure

All four papers make the reader cross the same conceptual bridge:

1. **Begin with a recognizable promise.** More depth should help; optimization theory should explain optimizers; a compute-agnostic schedule should be useful; faster optimizers should be adopted.
2. **Expose a concrete tension.** A deeper plain network has higher training error; real optimizer trajectories oscillate outside the regime covered by traditional theory; WSD's stable-phase loss looks worse before dropping; published optimizer speedups do not survive realistic comparison.
3. **Show why the easy explanation is insufficient.** The ResNet degradation is not overfitting and is not merely vanishing gradients. Central Flows shows that local stability assumptions miss the actual regime. River Valley explains why visible loss can hide progress. Fantastic Optimizers identifies tuning and evaluation confounds.
4. **Introduce one memorable conceptual object.** Residual learning, a central flow, a river valley, or a rigorous multi-scale benchmark. The name compresses the paper's mental model.
5. **Explain the mechanism before exhausting detail.** Learning a residual makes identity easy; time averaging turns chaotic motion into a tractable path; high learning rate advances along the river while decay removes hill oscillation; matched tuning removes artificial speedups.
6. **Turn the mechanism into discriminating consequences.** The paper states what should be observed if its picture is right.
7. **Arrange evidence as a logical test, not a data dump.** Controlled comparisons establish the core claim; scale, domains, ablations, or special cases probe generality and failure modes.
8. **End with a changed mental model.** Depth is an optimization problem solved by reformulation; oscillation can create useful implicit regularization; apparently bad short-term loss can hide progress; optimizer rankings depend on scale and evaluation design.

The transferable pattern is therefore:

> concrete tension -> inadequate standard picture -> named conceptual move -> intuitive mechanism -> formal or operational consequences -> decisive evidence -> boundary and changed mental model

## What each paper contributes to the pattern

### ResNet: constructive contradiction and minimal intervention

- The introduction turns “deeper is better” into a sharp question: why is stacking layers not enough?
- It uses a constructive argument: the deeper model contains a solution at least as good as the shallower model by setting added layers to identity. Higher training error therefore reveals an optimization failure, not a lack of representational capacity.
- The method is a minimal reformulation, from learning an unreferenced mapping to learning a residual around identity.
- The implementation preserves the comparison: identity shortcuts add essentially no parameters or computational complexity.
- The experiment order mirrors the claim order: establish degradation in plain nets, show its reversal in matched residual nets, then test depth, another dataset, and downstream tasks.

Use this pattern when a method paper can derive its intervention from a contradiction or constructed baseline.

### Central Flows: dynamics, derivation, interpretation

- The paper defines a high standard for theory: numerical prediction of trajectories on practical networks, not only qualitative convergence statements.
- It separates a hard microscopic object from a useful macroscopic one: the exact oscillatory path is difficult, while the time-averaged path is tractable.
- Major technical sections repeat a powerful rhythm: describe the optimizer's observed dynamics; derive the central flow; interpret what the flow says about the optimizer.
- Cartoons and annotated trajectories establish causal intuition before dense derivations.
- Ablated flows isolate mechanisms such as curvature regularization, while an explicit limitations section catalogs breakdowns.

Use this pattern for explanatory theory: phenomenon -> simplified analytical object -> derivation -> numerical fidelity -> mechanism-revealing ablation.

### River Valley: question, metaphor, theorem, intervention

- A practical constraint and a strange loss curve lead to an explicit central question.
- A single spatial metaphor decomposes the phenomenon into two components: progress along the river and oscillation up the hillsides.
- The introduction states two operational consequences—sustained high learning rate and final low learning rate—before the theorem details.
- The theory is connected to multiple empirical predictions, a toy data-generating explanation, and finally a revised learning-rate schedule.
- The method is not appended arbitrarily; it follows from noticing that the decay phase also makes river-direction progress.

Use this pattern when a conceptual model both explains observations and suggests an intervention: anomaly -> metaphor/decomposition -> formal predictions -> probes -> mechanism-derived method.

### Fantastic Optimizers: evaluation design as the contribution

- The paper starts with an adoption gap: large speedup claims coexist with little practical adoption.
- It identifies methodological confounds rather than assuming a new algorithm is needed.
- The introduction turns the study into explicit questions about tuning and scaling regimes.
- A controlled protocol, a grid over model sizes and data-to-model ratios, and end-of-training evaluation define what “fair” means operationally.
- Results are organized as lessons and robust patterns, not as a chronological lab notebook.
- Negative findings become useful because the evaluation protocol makes them credible.

Use this pattern for benchmark or measurement papers: claim/adoption gap -> confounds -> fairness contract -> systematic measurement grid -> robust lessons -> recommendations.

## Shared presentation techniques

- **The first figure is a graphical abstract.** It shows the anomaly, the conceptual move, or the main results. Captions begin with the claim the figure supports.
- **Names do intellectual work.** “Residual,” “central flow,” “river valley,” and “matrix-based” let later prose remain compact and consistent.
- **Introductions are miniature papers.** They include the setting, tension, idea, mechanism, contributions, evidence, and scope.
- **Section openings state their contract.** The reader is told what question the section answers and, in longer sections, how the subsections fit together.
- **Intuition precedes formalism, but formalism earns the claim.** Metaphors and cartoons orient the reader; equations, controls, and theorems make the claim checkable.
- **Evidence is matched to the causal story.** Comparisons are selected to rule out plausible alternatives, not only to maximize a headline number.
- **Limitations strengthen the contribution.** The best papers state the regime in which the conceptual picture is expected to work and show some failures.

## Important differences

Do not mistake common logic for one mandatory paper shape.

- ResNet is a compact method paper and has no conventional conclusion in its main body.
- Central Flows is a long explanatory theory paper with recurring derivation and interpretation sections.
- River Valley mixes theory, mechanistic data modeling, and a method inspired by the theory.
- Fantastic Optimizers is an empirical methodology paper whose main novelty is measurement discipline.

Choose the genre that matches the actual contribution. Do not add a theorem, benchmark grid, metaphor, or method merely because an exemplar contains one.
