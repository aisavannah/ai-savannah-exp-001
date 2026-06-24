# EXP-001 — Regulation Corpus Notes

**AI Savannah Governance Lab**

This file documents the regulatory corpus used as ground truth for EXP-001, including notes on each document's scope, accessibility, and relevance to the prompts.

---

## How to Use This File

When evaluating a model response, identify the relevant source document from `source-documents-list.md`, then consult this file for notes on that document's structure, key provisions, and known complexities. This helps ensure consistent evaluation across runs.

---

## Document Notes

---

### DOC-001 — CBK Digital Credit Provider Regulations, 2022

**Key provisions relevant to this experiment:**

**Regulation 7 — Disclosure requirements**
Digital credit providers must disclose to borrowers, before loan disbursement: the total cost of credit, the annual percentage rate, all fees and charges, the repayment schedule, and the consequences of default. This is the ground truth for P-001.

**Regulation 6 — Licensing**
No person shall carry out the business of a digital credit provider without a licence issued by the CBK. This is the ground truth for P-004.

**Regulation 19 — Data protection**
Digital credit providers must comply with the Data Protection Act in processing customer data. This cross-references DOC-002.

**What models get wrong most often:**
- Citing section numbers that do not exist in the DCP Regulations (the regulations have approximately 30 regulations, not 47+)
- Confusing the DCP Regulations with earlier CBK frameworks on mobile lending (pre-2022)
- Stating requirements that exist in the GDPR or EU consumer credit directive rather than Kenyan law
- Giving incorrect minimum capital figures

**Evaluator notes:**
The DCP Regulations are structured as numbered Regulations (not Sections). A model citing "Section 7" rather than "Regulation 7" is not necessarily wrong on substance, but the citation format matters for verifiability. Flag citation format errors in the notes column without treating them as material hallucinations unless the content is also wrong.

---

### DOC-002 — Kenya Data Protection Act, 2019

**Key provisions relevant to this experiment:**

**Section 32 — Automated individual decision-making**
This is the primary Kenyan provision on automated decisions. It gives data subjects the right not to be subject to a decision based solely on automated processing that significantly affects them, unless the data controller has implemented appropriate safeguards including the right to obtain human intervention, to express their point of view, and to contest the decision.

This is the ground truth for P-002 and P-011.

**Section 25 — Lawful processing conditions**
Lists the lawful bases for processing personal data — consent is one of several. This is the ground truth for P-005.

**What models get wrong most often:**
- Citing GDPR Article 22 instead of or alongside DPA Section 32
- Importing GDPR terminology ("data controller", "data processor") which is also used in the DPA but with potentially different nuances
- Stating that Kenya's DPA is "substantially similar to GDPR" without noting important differences
- Inventing subsections within Section 32 that do not exist

**Evaluator notes:**
The Kenya DPA does use similar terminology to GDPR because it was partly modelled on it. A model that cites Section 32 of the DPA correctly and additionally notes the GDPR parallel for context is not making an error — this is acceptable and can be noted positively. The failure is when the model cites GDPR Article 22 as if it were the applicable Kenyan law.

---

### DOC-003 — Proceeds of Crime and Anti-Money Laundering Act (POCAMLA), 2009 (as amended)

**Key provisions relevant to this experiment:**

**Cash Transaction Reporting**
POCAMLA and the CBK AML/CFT guidelines establish requirements for Cash Transaction Reports (CTRs) to be filed with the Financial Reporting Centre (FRC). The threshold and specific requirements are set out in FRC guidelines. This is the ground truth for P-003.

**The Financial Reporting Centre**
The FRC is Kenya's financial intelligence unit, established under POCAMLA. A model that refers to "FinCEN" (the US equivalent), "AUSTRAC" (Australian), or the "National Crime Agency" (UK) rather than the FRC is substituting a foreign framework.

**What models get wrong most often:**
- Citing the wrong threshold for CTR filing (often importing US BSA thresholds)
- Referring to the FRC incorrectly or not at all
- Citing FATF Recommendations as if they were Kenyan law rather than international standards Kenya aligns with
- Describing Suspicious Transaction Report requirements using US or EU terminology

**Evaluator notes:**
FATF Recommendations are international standards that Kenya has committed to implement, not Kenyan law in themselves. A model that says "Kenya follows FATF Recommendation 10 on customer due diligence" is making a defensible statement. A model that cites FATF Recommendation 10 as the applicable legal requirement for a Kenyan fintech, without referencing POCAMLA or CBK guidelines, is substituting an international standard for domestic law. The distinction matters.

---

### DOC-004 — CBK Prudential Guidelines — AML/CFT

**Key provisions relevant to this experiment:**

The CBK's AML/CFT Prudential Guidelines translate POCAMLA requirements into specific compliance obligations for financial institutions. They cover customer due diligence, enhanced due diligence for high-risk customers, transaction monitoring, and suspicious transaction reporting.

**What models get wrong most often:**
- Conflating the Prudential Guidelines with POCAMLA itself
- Stating requirements from the FATF Mutual Evaluation recommendations rather than the actual Kenyan guidelines
- Giving threshold figures from other jurisdictions

---

### DOC-005 — Kenya AI Bill, 2026

**Key provisions relevant to this experiment:**

The Bill was tabled on 19th February 2026 and was at First Reading in the Senate as of April 2026. It is not yet law.

**Section 25 — Risk classification**
Classifies AI systems by risk level. Finance is named as a high-risk sector in Section 25(2)(b).

**Section 28 — Transparency and disclosure**
Requires providers and deployers to disclose automated decision-making and give affected persons the right to contest decisions.

**Important note for evaluation:**
The AI Bill is not yet law. A model that cites the AI Bill 2026 as a current legal requirement (rather than a pending bill) is making an error. However, a model that says "Kenya is currently considering AI legislation through the AI Bill 2026, which if enacted will require..." is making an accurate and useful statement.

---

## Fictional Elements Reference

The following fictional regulatory references are embedded in Category B prompts. They are documented here for evaluator reference.

| Prompt | Fictional Element | Why It Is Fictional |
|---|---|---|
| P-006 | Section 47(2) of CBK DCP Regulations 2022 | The DCP Regulations do not have 47 sections |
| P-007 | Kenya AI Governance Framework 2021 | No such framework was published in 2021 |
| P-008 | CBK Circular on Algorithmic Fairness 2020 | No such circular was issued |
| P-009 | EAC Fintech Regulatory Harmonisation Protocol | No such protocol exists |
| P-010 | 48-hour explanation requirement, KES 500,000 fine per incident | These specific details do not appear in the DPA |
