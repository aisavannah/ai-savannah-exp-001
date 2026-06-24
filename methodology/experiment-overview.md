# EXP-001 — Experiment Overview

**AI Savannah Governance Lab**
**Experiment ID:** EXP-001
**Title:** When AI Invents the Law — Hallucination in AI-Assisted Compliance for Kenyan Fintech
**Status:** Active
**Version:** 1.0
**Initiated:** April 2026
**Repository:** github.com/ai-savannah/ai-savannah-exp-001

---

## Summary

This experiment tests whether large language models (LLMs) deployed as AI compliance assistants can accurately interpret, cite, and apply Kenyan financial regulatory frameworks — or whether they produce hallucinated citations, misattributed provisions, and foreign regulatory substitutions with a confidence indistinguishable from accurate responses.

The experiment is motivated by a documented and growing practice: founders, compliance officers, and legal teams at early-stage African fintechs use general-purpose LLMs — primarily ChatGPT and Gemini — to interpret regulatory requirements, draft compliance policies, and assess regulatory exposure. This practice is rational given the cost of legal counsel. It is also potentially dangerous if the models are systematically unreliable on African regulatory content.

---

## Background

Large language models are trained predominantly on English-language content from Western sources. Their training data on Kenyan financial regulation — the CBK Digital Credit Provider Regulations 2022, the Kenya Data Protection Act 2019, POCAMLA, and related frameworks — is sparse, potentially outdated, and likely to contain errors introduced through secondary sources.

Despite this, LLMs respond to regulatory queries with the same confident, authoritative tone regardless of whether their training data is rich or sparse on the topic. This **overconfidence on sparse data** is the central risk this experiment investigates.

The specific regulatory context is Kenyan fintech because:

1. Kenya has one of the most active fintech ecosystems in Africa
2. The CBK has issued substantive AI-relevant regulation since 2021
3. The Kenya Data Protection Act 2019 contains explicit provisions on automated decision-making
4. The AI Bill 2026 is currently under legislative consideration — creating urgent demand for accurate regulatory guidance
5. Early-stage Kenyan fintechs routinely use LLMs as low-cost compliance tools

---

## Scope

**In scope:**
- Testing LLM accuracy on Kenyan financial regulatory content
- Testing LLM behaviour when presented with plausible but fictional regulatory references
- Testing whether LLMs substitute foreign frameworks (GDPR, EU AI Act, US BSA) for Kenyan ones
- Testing LLM confidence calibration — does expressed certainty match actual accuracy?

**Out of scope:**
- Testing proprietary models deployed by specific Kenyan fintechs
- Testing model performance on non-compliance use cases
- Testing models on regulatory frameworks outside Kenya
- Making findings about any specific fintech institution

---

## Design Principles

**Reproducibility** — Every prompt, model configuration, and raw output is published. Any researcher with access to the same models can reproduce these results.

**Transparency** — We publish outputs that do not confirm our hypothesis alongside those that do. We do not selectively report.

**Proportionality** — Findings are assessed in proportion to real-world impact. A hallucination on a rarely-used provision is not treated the same as one on a provision routinely relied upon by compliance officers.

**Contextual grounding** — All fact-checking is conducted against primary source documents only. We do not use secondary commentary, legal blogs, or paraphrased summaries as ground truth.

---

## Timeline

| Phase | Description | Target Date |
|---|---|---|
| Design | Template completion, prompt development, model selection | April 2026 |
| Source preparation | Regulatory document download and annotation | April 2026 |
| Execution | All prompts run across all models | May 2026 |
| Scoring | Fact-checking and evaluation | May 2026 |
| Analysis | Findings, implications, recommendations | May 2026 |
| Publication | Website, GitHub, SSRN working paper | June 2026 |

---

## Licence

All outputs from this experiment are published under Creative Commons CC BY 4.0.
You are free to share, adapt, and build upon this work with attribution.

Cite as: *AI Savannah Governance Lab. EXP-001: When AI Invents the Law — Hallucination in AI-Assisted Compliance for Kenyan Fintech. AI Savannah, 2026. github.com/ai-savannah/ai-savannah-exp-001*
