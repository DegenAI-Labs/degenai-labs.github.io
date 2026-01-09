---
layout: project
title: "Hallu-Bench"
slug: hallu-bench
status: active
since: 2026-01
tags: [evaluation, hallucination, benchmarks]
---

A unified “world-model” definition of hallucination that makes sources of truth explicit and enables scalable benchmarks in fully-specified environments.

## Motivations
Hallucination has become an overloaded term across translation, summarization, open-domain QA, retrieval-augmented generation, multimodal models, and agentic systems—often meaning different things depending on the task. This fragmentation makes it hard to compare benchmarks, interpret mitigation results, or even agree on what counts as a hallucination versus a planning or instruction-following failure. Our motivation is to put these scattered notions on a single foundation by making the implicit assumptions explicit: what the system treats as “truth,” what evidence it is allowed to use, and how conflicts between sources should be resolved.

## Overview
We propose a unified definition of hallucination as inaccurate internal world modeling that becomes observable through a model’s outputs—formalized as the production of at least one false atomic claim under a specified reference world. Concretely, any hallucination judgment is parameterized by (i) a reference world model 𝑊 (the source of truth, e.g., a document, knowledge base, or environment state), (ii) a view function 𝑉 (what information is visible/available to the model for a given input), and (iii) a conflict policy 𝑃 and resulting truth function 𝑇 (how contradictions are resolved and claims are labeled true/false/unknown). Under this lens, many prior definitions become special cases that differ mainly in their choices of 𝑊, 𝑉, and 𝑃.

Building on the formalism, we outline a path toward a family of scalable hallucination benchmarks grounded in synthetic or simulator-defined environments where 𝑊 is fully specified and truth labels can be computed by construction. This enables controlled stress tests across difficulty, partial observability, long interaction histories, and conflicting evidence—while cleanly separating hallucinations (belief/world-model errors) from other failure modes like poor planning or incentive-driven overconfidence.
