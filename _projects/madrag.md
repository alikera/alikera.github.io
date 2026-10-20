---
layout: page
title: Multi-agent debate for essay scoring
description: Advocate, Skeptic and Judge agents score essays without task-specific training.
img: assets/img/projects/madrag.jpg
importance: 1
category: research
related_publications: true
---

Automated essay scoring usually depends on supervised models trained for one prompt and one rubric, and a single LLM asked to grade an essay tends to drift toward the middle of the scale and gives little explanation for its score. This line of work, which I lead as first author in the Digital Learning Lab at UC Irvine, asks whether structured interaction between several LLM agents can produce trait-level scores that are both more reliable and easier to inspect.

**MADEST** (2025) compared three multi-agent designs for trait-level essay scoring: a supervisor that delegates sub-traits to rater agents, rater–reviewer collaboration, and debate between an Advocate (strengths), a Skeptic (weaknesses) and a Judge, with first-token log-probabilities used as a confidence signal when the Judge weighs the two sides {% cite keramati2025madest %}. In that evaluation the debate design outperformed the other two, and its agreement with human raters was on a par with the agreement between the two human raters. I presented the comparison as a contributed talk in the NeurIPS 2025 Education Program {% cite keramati2025essayscoring %}.

**MADRAG** (NLP4DH 2026, co-located with ACL) adds retrieval-augmented grounding: before deciding, the Judge compares the essay with retrieved, rubric-aligned scored exemplars {% cite keramati2026madrag %}. On ASAP essay sets 7 and 8, MADRAG substantially outperforms prompt-based LLM baselines and approaches supervised systems without any fine-tuning. Ablations show that retrieval drives the calibration gains, while debate mainly improves higher-level traits such as Ideas and Organization. A qualitative error analysis in the paper catalogues the remaining failure modes, for example a Judge captured by one debater's framing, which motivated the confidence-diagnostics work described in the next project.

The debate approach also informs the Multi-Agent Review feature of PapyrusAI, the lab's AI writing coach, and the scorer's evaluation is preregistered on the Open Science Framework ([osf.io/7qpwg](https://osf.io/7qpwg)). MADRAG was designed and evaluated with Shiyuan Zhou, Sharad Mehrotra and Mark Warschauer.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/madrag-fig.jpg" title="MADRAG scoring pipeline" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The MADRAG pipeline: a supervisor assigns rubric traits to debating teams; for each trait an Advocate and a Skeptic argue, and a Judge grounded in retrieved scored essays issues the score (figure from the NLP4DH 2026 paper).
</div>

**Links:** [MADRAG paper (arXiv)](https://arxiv.org/abs/2606.06754) · [ACL Anthology](https://doi.org/10.18653/v1/2026.nlp4dh-1.30) · [MADEST poster (Zenodo, CC BY 4.0)](https://doi.org/10.5281/zenodo.17196206) · [NeurIPS 2025 talk recording](https://slideslive.com/39055005/)
