# IQ:NS — Finance Sector

Financial services AI operates under the most structurally mature regulatory environment of any sector: Basel model risk management, EBA AI governance guidelines, SR 11-7 supervisory expectations, and DORA's operational resilience requirements now explicitly intersect with AI governance. Banks, asset managers, and insurers face dual exposure — sector-specific model risk frameworks plus horizontal AI regulation — creating a compliance matrix that is uniquely complex and commercially consequential.

---

## Who This Is For

| Persona | Pain Point |
|---|---|
| Chief Risk Officer / Model Risk Manager | Validating AI models against SR 11-7 and EBA GL expectations simultaneously |
| Head of Compliance / Regulatory Affairs | Mapping EU AI Act High-Risk (Annex III: credit scoring, insurance pricing) to existing Basel/EBA controls |
| AI / Quant / Data Science Lead | Understanding which technical validation requirements apply to credit, fraud, and AML models |
| Internal Audit | Ensuring model inventory and governance programme covers all regulatory frameworks |
| Regtech / GRC Platform Team | Automating compliance evidence generation for examiners |

---

## Regulatory Surface

| Framework | Key Finance Exposure |
|---|---|
| **EBA AI Guidelines** (`eba-ai`) | Human oversight, model explainability, data governance for credit institutions — directly enforceable |
| **SR 11-7** (`sr-11-7`) | US Federal Reserve supervisory guidance on model risk — the baseline for US bank AI governance |
| **EU AI Act Annex III** | Credit scoring, insurance pricing, and employment AI explicitly listed as high-risk — full Title III applies |
| **EU GDPR AI** (`eu-gdpr-ai`) | Automated decision-making and profiling (Art. 22) — directly triggered by retail credit AI |
| **NIST AI RMF** | Increasingly cited in OCC and CFPB examination frameworks |
| **ISO 42001** | Certification track for AI management systems — demanded by large institutional clients |
| **OECD AI** | Soft-law baseline referenced by IOSCO and FSB in cross-border AI guidance |

---

## High-Value Use Cases

### 1. SR 11-7 × EU AI Act Unified Model Inventory
Financial institutions operating in both the US and EU must satisfy SR 11-7's model risk management expectations and EU AI Act Title III simultaneously. These frameworks have substantial overlap but different vocabulary and emphasis.

```sparql
# Cross-framework equivalents: SR 11-7 controls ↔ EU AI Act obligations
# → ai/sparql/04-cross-framework-equivalents.rq

# Gap analysis: what EU AI Act requires that SR 11-7 programme doesn't cover
# → ai/sparql/08-gap-analysis-dimensions.rq  (framework1=sr-11-7, framework2=eu-ai-act)

# Controls by dimension — explainability (critical for adverse action notices)
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Explainability)
```

**Outcome:** Single unified model governance framework that satisfies both US examiners and EU notified bodies — eliminates the parallel-track compliance overhead.

### 2. Credit Scoring AI — High-Risk Determination and Obligation Register
EU AI Act Annex III, point 5(b) explicitly names AI systems for creditworthiness assessment as high-risk. Combined with GDPR Art. 22 automated decision obligations, the compliance surface is dense.

```sparql
# All high-risk obligations — filter to eu-ai-act
# → ai/sparql/02-high-risk-obligations.rq

# Stakeholder obligations: who is the provider vs. deployer vs. operator?
# → ai/sparql/10-obligations-by-stakeholder.rq

# Human oversight requirement — mandatory for adverse action scenarios
# → ai/sparql/A-03-ask-human-oversight-covered.rq

# Prohibited practices — check biometric-based credit scoring rules
# → ai/sparql/06-prohibited-practices.rq
```

**Outcome:** Article-cited obligation register for regulatory examination, audit committee, and external counsel — replaces weeks of manual legal research.

### 3. AML / Fraud Detection Model Governance
AML models are expressly flagged by FATF and national supervisors as high-risk AI applications requiring explainability and human review. EBA guidelines require documented validation and ongoing monitoring.

```sparql
# Lifecycle requirements for deploy and monitoring phases
# → ai/sparql/05-requirements-by-lifecycle.rq  (filter: Monitor)

# Risk register — risks in the accountability and transparency dimensions
# → ai/sparql/09-risks-by-category.rq

# Construct risk register for regulatory examination pack
# → ai/sparql/C-03-construct-risk-register.rq
```

### 4. DORA AI Operational Resilience
DORA (Digital Operational Resilience Act) operational resilience obligations increasingly intersect with AI systems classified as critical ICT. Incident response, third-party AI vendor oversight, and continuity planning all have AI-specific dimensions.

```sparql
# Controls in the Robustness and Reliability dimensions
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Robustness, ai:Reliability)

# Third-party / supply-chain risks
# → ai/sparql/09-risks-by-category.rq
```

### 5. Regulatory Examination Evidence Pack
OCC, ECB, FCA, and MAS examiners increasingly request structured AI governance documentation. IQ:NS generates this programmatically.

```sparql
# Full compliance profile for an AI system
# → ai/sparql/C-01-construct-compliance-profile.rq

# Assessment types — what validation activities are required?
# → ai/sparql/12-assessment-types.rq
```

**Outcome:** Examination-ready evidence pack with regulatory citations, reducing exam preparation from weeks to hours.

---

## Key Dimensions for Financial AI

`ai:Explainability` · `ai:Fairness` · `ai:Accountability` · `ai:Transparency` · `ai:Robustness` · `ai:HumanOversight` · `ai:Reliability`

---

## Sector-Specific Graph Extensions Needed

| Gap | Priority |
|---|---|
| DORA AI provisions (mapped as ai:Controls) | High — operational resilience is now mandatory |
| CFPB / OCC model risk AI guidance (US) | High — examination expectations are evolving faster than the graph |
| IOSCO AI in asset management principles | High — buy-side AI governance required |
| Insurance sector (EIOPA AI guidelines) | Medium — pricing and underwriting AI obligations |
| Basel IV AI model validation standards | Medium — IRB model governance intersection |

---

## Quick Wins

- **Examiner briefing package:** `C-01-construct-compliance-profile.rq` → structured compliance posture in under an hour
- **Adverse action explainability:** query `ai:Explainability` controls instantly for FCRA / GDPR Art. 22 documentation
- **Model inventory gap scan:** `08-gap-analysis-dimensions.rq` run quarterly to catch obligation drift as regulations update
- **Board risk committee report:** `C-03-construct-risk-register.rq` → XLSX-ready risk register with framework citations
