---
layout: project
title: "Scaling Laws"
slug: scaling-laws
status: active
since: 2026-01
tags: [scaling]
---

Mapping the trade-off between parametric pretraining and retrieval-augmented memory under fixed data budgets.

## Motivations
Large language models store vast amounts of world knowledge in their parameters, but this comes at significant computational and financial cost. At the same time, retrieval-augmented generation (RAG) systems offer a way to offload factual knowledge into external memory, potentially reducing the need for extensive pretraining. Despite this, there is little systematic understanding of how much knowledge should be learned parametrically versus retrieved at inference time, especially under a fixed data or compute budget. This project aims to characterize that trade-off and identify regimes where retrieval meaningfully substitutes for pretraining, as well as thresholds where models become capable of effectively using retrieved evidence.

## Overview
We study the interaction between pretraining scale and retrieval by training decoder-only language models of varying sizes on controlled splits of a fixed corpus. For each experiment, a fixed token budget is allocated between model pretraining and an external retrieval index, producing a family of pretrain–retrieval mixtures (e.g., 100% pretraining, 70/30 pretrain–retrieval, 30/70, etc.). Models are trained without retrieval and evaluated at test time using hybrid RAG pipelines built from the retrieval portion of the data. This setup allows us to directly measure how reallocating tokens from parametric learning to external memory affects downstream performance.

We evaluate across a diverse set of tasks, including factual question answering, reasoning, and multi-hop knowledge tasks, and analyze performance as a function of model size and data allocation. Our goal is to identify “knee points” where additional pretraining yields diminishing returns and retrieval becomes more effective, as well as task-dependent differences in these transitions. By mapping these trade-offs, the project aims to inform more compute-efficient training strategies and provide empirical grounding for how knowledge should be distributed between model weights and external memory in large language systems.
