---
layout: page
title: Simulating students' Java errors with LLMs
description: Can LLMs stand in for students by producing realistic buggy code? (EDM 2026)
img: assets/img/projects/java-errors.jpg
importance: 5
category: research
related_publications: true
---

Understanding the errors students make is central to programming education, but a representative set of errors for a newly designed task only accumulates after extensive classroom deployment. With Jie Cao (co-first author), Iman Mohammadi, Mark Warschauer and Yang Shi, I asked whether large language models can serve as scalable proxies for students by simulating realistic logical errors in Java submissions {% cite keramati2026javaerrors %}.

We used the CodeWorkout dataset of more than 74,000 unique student Java submissions across 37 problems and evaluated five LLMs under three prompting strategies: direct input–output prompting, chain-of-thought, and an iterative Self-Refine loop in which the model critiques and revises its own simulated submissions. I designed the Self-Refine student simulator and the evaluation, which parses each submission into a syntax tree and uses tree-edit distance to measure two things: diversity (how many distinct error patterns a model produces) and alignment (how close its errors are to authentic student mistakes), broken down by how much students struggled with each task.

All models generate diverse errors, but their alignment with human submissions diverges, and Claude Sonnet 4 gave the most balanced trade-off. In a blinded expert annotation study (N = 401 submissions), annotators judged 164 of the 196 LLM-generated erroneous submissions from the selected configuration (Claude Sonnet 4 with Self-Refine) to be human-written (83.7%), although the synthetic and authentic error distributions still differed in shape. Harder problems elicited more diverse but less student-like errors. The paper was published as a short paper at the 19th International Conference on Educational Data Mining (EDM 2026).

Simulated learners can pre-populate feedback banks, test teachable agents and tutoring systems, and stress-test learning analytics before real students are involved.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/java-errors-fig.jpg" title="Fidelity-diversity trade-offs in simulated student errors" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Trade-offs between alignment with real student errors (fidelity) and diversity, by model and prompting technique (left) and by problem (right). Figure from the EDM 2026 paper.
</div>

**Links:** [Paper (arXiv 2606.14113)](https://arxiv.org/abs/2606.14113) · [EDM 2026 proceedings (Zenodo)](https://doi.org/10.5281/zenodo.21040050)
