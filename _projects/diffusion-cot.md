<!-- ---
layout: project
title: "Diffusion-CoT"
slug: diffusion-cot
status: active
since: 2026-01
tags: [diffusion, reasoning]
---

Comparing diffusion and autoregressive language models for robustness to corrupted reasoning.

## Motivations
Large language models typically generate text autoregressively, committing to each token one step at a time. While effective, this generation paradigm can be brittle for multi-step reasoning: mistakes early in a chain-of-thought often propagate and cannot be corrected. Diffusion-based language models offer a different approach, generating outputs by iteratively denoising a global representation rather than following a fixed left-to-right trajectory. This raises a natural question: are diffusion models inherently more robust to corrupted or imperfect reasoning traces? Furthermore, if they can repair messy reasoning chains, could diffusion language models become useful building blocks in multi-agent LLM systems, self-correcting chains, or tool-using models?

## Overview
In this project, we study the robustness of diffusion language models compared to autoregressive models on structured reasoning tasks. We compare an 8B autoregressive LLaMA model with an 8B diffusion language model (LLaDA) on math problems with multi-step chain-of-thought solutions. To stress-test robustness, we deliberately corrupt intermediate reasoning steps (e.g., shuffling, removing, or injecting steps) and evaluate whether models can still recover correct final answers.

We conduct both inference-only experiments and fine-tuning experiments, measuring final answer accuracy and qualitative reasoning repair behavior. By isolating the effect of the generation paradigm, this work aims to shed light on when and why diffusion-based text generation may offer advantages for robust reasoning. -->
