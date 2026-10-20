---
layout: page
title: Theory-of-mind assessment chatbot
description: A LLaMA-3 chatbot that administers the Faux Pas Recognition Test for autistic individuals.
img: assets/img/projects/tom-chatbot.jpg
importance: 6
category: research
related_publications: true
---

Theory of mind, the ability to infer other people's mental states, is commonly assessed with the Faux Pas Recognition Test: an administrator reads short social stories and asks whether someone said something they should not have, and why. The test depends heavily on a trained human administrator, which limits how often and for how many people it can be used. Difficulty detecting faux pas is common in autism spectrum disorder.

In a 2024 collaboration between the University of Tehran and the National Brain Center, I co-developed a chatbot built on LLaMA-3 that administers the test in conversation {% cite fallah2024theoryofmind %}. The system works in two phases. It first presents the stories and assesses the user's answers, following the structure of the standard test; it then follows the assessment with rehabilitative guidance that walks the user through the social cues they missed. Scoring combines automated evaluation by the model with human oversight to keep results accurate and consistent, and the system prompts are built around chain-of-thought prompting so that the model reasons explicitly about a story before judging a response.

The paper, published at the 14th International Conference on Computer and Knowledge Engineering (ICCKE 2024), reports that the chatbot could deliver dynamic and supportive theory-of-mind assessments and argues for broader use of LLM-powered chatbots in psychological practice. I co-developed the system as second of four authors, working with co-authors in neuroscience and psychiatry.

This was my first project at the boundary between language models and assessment under human oversight, a theme that runs through my later work on essay scoring and LLM-as-judge evaluation.

**Links:** [Paper (IEEE Xplore)](https://doi.org/10.1109/ICCKE65377.2024.10874775)
