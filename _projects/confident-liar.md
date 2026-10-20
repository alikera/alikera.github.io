---
layout: page
title: Confidence signals in multi-agent debate
description: Do token log-probabilities reveal when debating LLM agents reason badly?
img: assets/img/projects/confident-liar.jpg
importance: 2
category: research
related_publications: true
---

Multi-agent debate systems are usually judged only on whether the final answer is right. The intermediate reasoning is rarely measured, and an agent can argue confidently and still be wrong. In this series of first-authored papers with Justin Cheok, Jacob Horne and Mark Warschauer, I study whether a model's own token-level confidence (the log-probabilities of its reasoning tokens) predicts reasoning quality as scored by an LLM judge, and whether either signal tracks task correctness.

The framework pairs a two-agent debate (a Constructor that builds a case and an Auditor that challenges it; Advocate and Skeptic in the essay-scoring setting) with an LLM-as-judge that scores each agent's reasoning for instruction following, justification quality and evidence grounding, and raises a critical-failure flag when the reasoning breaks down.

Findings so far, in rubric-based essay scoring on two ASAP essay sets:

- Confidence follows a consistent four-phase trajectory over the course of a response, and the two agent roles behave differently: confidence aligns with judged reasoning quality roughly twice as strongly for the Constructor as for the Auditor, and confidence-based detection of critical reasoning failures is markedly more reliable for the Constructor (AUROC 0.804) than for the Auditor (0.634) {% cite keramati2026confidentliar %}.
- Confidence over the first few generated tokens is consistently the strongest predictor of judged reasoning quality, outperforming full-sequence statistics; the opening segment of a response is the most heterogeneous and therefore the most informative region {% cite keramati2026earlytoken %}. An earlier version of this analysis appeared as a poster at the ICLR 2026 Workshop on Logical Reasoning of Large Language Models {% cite keramati2026firsttokens %}.

The practical goal is a cheap monitoring layer for multi-agent scoring systems: a signal that is available at decoding time, costs no extra model call, and tells a system when a judge should look more closely.

In related work, I contributed to a LAK 2026 study that treats disagreement between LLM agents' reasoning traces as an analytic signal for qualitative coding in learning analytics {% cite tajik2026disagreement %}.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/confident-liar-fig.jpg" title="Confidence trajectories of the Constructor and Auditor agents" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Mean token-level confidence of the Constructor and Auditor agents across a response. The volatile opening tokens carry most of the signal about reasoning quality (figure from the ACL 2026 SRW paper).
</div>

**Links:** [The Confident Liar (ACL 2026 SRW)](https://doi.org/10.18653/v1/2026.acl-srw.121) · [arXiv](https://arxiv.org/abs/2606.10296) · [Early-Token Confidence (GEM 2026)](https://doi.org/10.18653/v1/2026.gem-main.60) · [The First Tokens Matter (OpenReview)](https://openreview.net/forum?id=0FOOrwSQ9E)
