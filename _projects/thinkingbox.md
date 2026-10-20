---
layout: page
title: ThinkingBox agent reliability benchmark
description: A sandbox and 507-task benchmark that grades tool-using agents on final system state.
img: assets/img/projects/thinkingbox.jpg
importance: 4
category: research
related_publications: true
---

Agent benchmarks tend to credit a single successful run and to score what the agent says or which tool it calls. Real work beyond code is stateful: an agent has to gather missing information over several turns, follow domain policies, coordinate dependent tools, and leave the backend in exactly the right state with no collateral effects. During my 2026 applied-scientist internship at Microsoft (Copilot Studio), I contributed to **ThinkingBox**, an open-source sandbox for tool–agent–user interaction, and co-developed **ThinkingBox-Bench**, its reliability benchmark {% cite li2026thinkingbox %}.

ThinkingBox runs each task in an isolated, MCP-compatible tool session with a stateful backend, records the complete execution trace, and grades the outcome with executable checks on the terminal backend state and side effects rather than on the final message. ThinkingBox-Bench contains 507 policy-conditioned workflows across five business domains (retail, hospitality, auto insurance, neobank internal IT, and consulting IT/HR support); 477 tasks are graded on state alone and 30 add a response rubric. I built the simulated user that plays the customer or employee and the LLM-judge evaluators, and I am a co-first author of the paper. The core framework was initiated and built by colleagues at Microsoft before my internship.

The headline finding is a large gap between discovering a solution and reliably producing one. With 20 independent attempts per task, Claude Opus 5 succeeds on 66.5% of single attempts but on all 20 attempts for only 47.5% of tasks; Kimi-K3, the strongest open-weight model, falls from 57.4% to 17.6% by the paper's estimate. Many failed trials end cleanly after valid state-changing actions, so response- or tool-call-level signals are poor proxies for end-to-end completion. The benchmark (v1.0, August 2026) is released with MIT-licensed code and CDLA-Permissive-2.0 data, and the sandbox's executable verdicts also serve as rewards for reinforcement-learning post-training.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/thinkingbox-fig.jpg" title="ThinkingBox sandbox and the discovery-reliability gap" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Top: the sandbox loop, from simulated user and agent through the isolated tool session to executable judging. Bottom: for every model, the share of tasks solved on every one of 20 attempts (green) is far below first-try success (blue) and success on at least one attempt (orange). Figure from the arXiv paper.
</div>

**Links:** [Paper (arXiv 2608.19741)](https://arxiv.org/abs/2608.19741) · [github.com/microsoft/thinkingbox](https://github.com/microsoft/thinkingbox) · [github.com/microsoft/thinkingbox-data](https://github.com/microsoft/thinkingbox-data) · [Dataset on Hugging Face](https://huggingface.co/datasets/microsoft/ThinkingBox-Bench) · [Blog post](https://huggingface.co/blog/microsoft/thinkingbox)
