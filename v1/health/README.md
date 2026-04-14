# IQ:NS — Health Sector

Healthcare AI sits at the intersection of the highest-consequence risk classifications under every major framework: EU AI Act Annex III category 5 (biometric and medical), FDA Software as a Medical Device (SaMD), and sector-specific EBA and ONC trustworthy AI requirements. A misclassified imaging model or a flawed clinical decision support tool carries life-safety and regulatory consequences simultaneously.

---

## Who This Is For

| Persona | Pain Point |
|---|---|
| Chief Medical Officer / Clinical AI Lead | Validating that AI-assisted diagnosis tools meet safety and oversight requirements |
| Regulatory Affairs Manager | Aligning SaMD submissions with FDA AI/ML action plan and EU MDR |
| Health IT / Interoperability Engineer | Understanding data governance obligations at the point of AI inference |
| Hospital CIO | Demonstrating AI governance posture to CMS, HIPAA auditors, and accreditation bodies |
| Digital Health Startup (Series A–C) | Meeting procurement requirements from NHS, VA, or large health systems |

---

## Regulatory Surface

| Framework | Key Healthcare Exposure |
|---|---|
| **FDA AI/ML SaMD** (`fda-aiml-samd`) | Predetermined Change Control Plans, continuous learning oversight, post-market surveillance |
| **EU AI Act Annex III** | Medical devices explicitly named as high-risk AI — full Title III obligations apply |
| **ONC Trustworthy AI** (`onc-trustworthy`) | US interoperability and non-discrimination requirements for health AI |
| **ISO 42001** | Management system baseline increasingly required by NHS Digital and US health systems |
| **NIST AI RMF** | Bias and fairness controls — critical for diagnostic AI equity |
| **EU GDPR AI** (`eu-gdpr-ai`) | Special category data (Art. 9) processing for health records |
| **IEEE 7000** | Ethical impact assessment — procurement requirement for academic medical centres |

---

## High-Value Use Cases

### 1. SaMD Pre-Submission Compliance Map
Before an FDA 510(k) or De Novo submission, map the AI/ML system's controls to the FDA AI/ML Action Plan and EU AI Act simultaneously.

```sparql
# All high-risk obligations — filter to fda-aiml-samd
# → ai/sparql/02-high-risk-obligations.rq

# Human oversight coverage (mandatory for SaMD)
# → ai/sparql/A-03-ask-human-oversight-covered.rq

# Lifecycle requirements — design, training, validation, post-market
# → ai/sparql/05-requirements-by-lifecycle.rq
```

**Outcome:** Pre-submission obligation register keyed to specific FDA guidance sections and EU AI Act articles; reduces regulatory counsel hours by 60–80%.

### 2. Clinical Decision Support Risk Classification
Determine whether a CDS tool falls under EU AI Act Annex III (automatic high-risk) or qualifies for lighter obligations.

```sparql
# Prohibited practices check — rule out categorical prohibition first
# → ai/sparql/06-prohibited-practices.rq

# Construct full compliance profile for the system
# → ai/sparql/C-01-construct-compliance-profile.rq
```

**Outcome:** Defensible regulatory classification memo with source citations — essential before clinical deployment.

### 3. Health Equity and Bias Audit
Regulators and health systems increasingly require documented bias assessments. IQ:NS maps fairness obligations across NIST AI RMF, ONC, and ISO 24027.

```sparql
# All fairness and bias controls, cross-framework
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Fairness)

# Risks in the fairness category
# → ai/sparql/09-risks-by-category.rq  (filter: ai:Fairness)
```

**Outcome:** Structured bias audit framework with provenance to regulatory source — required for CMS value-based care AI programmes.

### 4. Post-Market Surveillance Obligation Register
FDA's Predetermined Change Control Plan and EU AI Act Art. 72 post-market monitoring — both require documented surveillance obligations.

```sparql
# Requirements scoped to deploy and monitor lifecycle stages
# → ai/sparql/05-requirements-by-lifecycle.rq  (filter: ai:Deploy, ai:Monitor)

# Stakeholder obligations (manufacturer vs. deployer vs. operator)
# → ai/sparql/10-obligations-by-stakeholder.rq
```

### 5. NHS / Large Health System Procurement Response
UK and EU public health system procurement increasingly requires ISO 42001 alignment and DTAC (Digital Technology Assessment Criteria) equivalence.

```sparql
# Gap analysis: ISO 42001 vs. existing programme
# → ai/sparql/08-gap-analysis-dimensions.rq

# Cross-framework equivalents — show where controls satisfy multiple frameworks
# → ai/sparql/04-cross-framework-equivalents.rq
```

---

## Key Dimensions for Healthcare AI

`ai:Safety` · `ai:Fairness` · `ai:HumanOversight` · `ai:Transparency` · `ai:Privacy` · `ai:Reliability` · `ai:Accountability`

---

## Sector-Specific Graph Extensions Needed

| Gap | Priority |
|---|---|
| EU MDR / IVDR AI provisions | High — medical device regulation not yet mapped |
| CMS billing AI rules (US) | High — fraud detection AI faces separate obligations |
| HIPAA AI inference constraints | High — de-identification requirements at inference time |
| NHS DTAC / DCB 0129 | Medium — UK clinical risk management standard |
| WHO AI in health guidance | Medium — procurement baseline for global health |

---

## Quick Wins

- **Board / IRB presentation:** `C-03-construct-risk-register.rq` → structured risk register in 10 minutes
- **Vendor due diligence questionnaire:** query by dimension to answer standard NHS/VA AI supplier questionnaires automatically
- **Clinical trial AI oversight:** `A-03-ask-human-oversight-covered.rq` → instant protocol compliance check
