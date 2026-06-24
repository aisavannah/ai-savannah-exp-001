# EXP-001 — Research Questions

**AI Savannah Governance Lab**

---

## Primary Research Question

> Do large language models produce materially accurate responses when asked to interpret and cite Kenyan financial regulatory frameworks, or do they hallucinate regulatory provisions with confidence indistinguishable from accurate responses?

---

## Secondary Research Questions

### RQ2 — Fictional Reference Detection
> When presented with a plausible but entirely fictional regulatory reference embedded in a prompt, do LLMs identify and correct the fictional premise — or do they accept and elaborate on it?

This question tests a specific and dangerous failure mode: a compliance officer who has half-remembered a provision incorrectly uses an LLM to "confirm" it. Does the model catch the error or compound it?

### RQ3 — Foreign Framework Substitution
> When asked about Kenyan regulatory requirements on a topic where a well-documented foreign framework exists (GDPR, EU AI Act, US Bank Secrecy Act), do LLMs apply the Kenyan framework or substitute the foreign one — and do they disclose when they are substituting?

This question tests regulatory misalignment. A model that answers a question about Kenyan data protection law by citing GDPR Article 22 — without disclosing it has switched frameworks — is producing dangerous misguidance.

### RQ4 — Confidence Calibration
> Does a model's expressed certainty in its regulatory responses correlate with the accuracy of those responses — or does it express equal confidence on accurate and hallucinated content?

This question tests the most dangerous property of LLM hallucination in compliance contexts: not that models are wrong, but that they are wrong with authority.

### RQ5 — Self-Assessment Accuracy
> When directly asked to assess the reliability of its own regulatory knowledge about Kenya, does a model accurately represent its limitations — or does it overstate its competence?

This question tests metacognition. A model that acknowledges "my knowledge of Kenyan regulation may be limited and should be independently verified" is safer than one that presents its outputs as authoritative without qualification.

---

## Hypotheses

### H1 — Primary Hallucination Hypothesis
*If LLMs are presented with specific, verifiable questions about Kenyan financial regulatory frameworks, then the majority of responses will contain at least one material factual error — including invented section numbers, misattributed provisions, or non-existent regulations — presented with full confidence.*

**Falsification condition:** H1 is falsified if fewer than 30% of responses to Category A prompts (accurate regulatory questions) contain material errors.

### H2 — Fictional Reference Hypothesis
*If LLMs are presented with prompts containing plausible but fictional regulatory references, they will accept and elaborate on the fictional premise rather than identifying it as non-existent in the majority of cases.*

**Falsification condition:** H2 is falsified if models correctly identify the fictional premise in more than 50% of Category B prompts.

### H3 — Foreign Framework Substitution Hypothesis
*If LLMs are asked about Kenyan regulatory requirements on topics where well-documented foreign frameworks exist, they will apply the foreign framework to the Kenyan context without adequate disclosure in the majority of cases.*

**Falsification condition:** H3 is falsified if models correctly apply Kenyan frameworks and disclose any foreign framework references in more than 50% of Category C prompts.

### H4 — Overconfidence Hypothesis
*LLMs will express similar levels of confidence on accurate regulatory responses and on responses containing material hallucinations — with no statistically meaningful difference in expressed certainty between correct and incorrect answers.*

**Falsification condition:** H4 is falsified if models consistently express lower confidence on responses that are found to contain material errors.

---

## What This Experiment Cannot Answer

This experiment tests general-purpose LLMs, not purpose-built compliance tools with curated regulatory databases. A finding that GPT-4o hallucinates Kenyan regulatory provisions does not prove that all AI compliance tools do so — only that this class of model does so in this context.

This experiment does not determine the technical cause of hallucinations — whether they result from absent training data, conflated training data, or model architecture. It documents that hallucinations occur and measures their frequency and character.

This experiment cannot prove that any specific Kenyan fintech has made compliance errors as a result of LLM hallucination. It demonstrates that the conditions for such errors exist in publicly available AI systems in common use.
