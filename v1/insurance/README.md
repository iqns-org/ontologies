# IQ:NS — Insurance

Insurance AI operates at the intersection of actuarial science, consumer protection law, and the emerging AI regulatory stack. Pricing, underwriting, claims automation, and fraud detection are all in scope for EU AI Act high-risk classification. EIOPA is finalising binding AI governance guidelines for EU insurers. Simultaneously, state insurance commissioners in the US are regulating algorithmic pricing through existing unfair trade practice statutes. No single framework document covers this crosswalk — IQ:NS does.

---

## Who This Is For

| Persona | Pain Point |
|---|---|
| Chief Actuary / Head of Pricing | Demonstrating that AI pricing models meet fairness and explainability obligations across jurisdictions |
| CRO / Model Risk Manager | Adapting SR 11-7-style model governance expectations to insurance-specific AI |
| Regulatory Affairs / Compliance | Navigating EIOPA AI guidelines, EU AI Act, and US state insurance commissioner requirements simultaneously |
| Claims Automation Lead | Ensuring AI-driven claims decisions meet consumer rights and explanation obligations |
| InsurTech / MGA | Meeting carrier and reinsurer AI due diligence requirements as a condition of capacity access |

---

## Regulatory Surface

| Framework | Key Insurance Exposure |
|---|---|
| **EU AI Act Annex III pt. 5(c)** | AI for insurance risk assessment and pricing explicitly listed as high-risk — full Title III obligations apply |
| **EBA AI Guidelines** (`eba-ai`) | Directly applicable to insurance undertakings under Solvency II scope; model risk principles carry over |
| **EU GDPR AI** (`eu-gdpr-ai`) | Art. 22 automated decision-making — individual underwriting and claims decisions at scale |
| **ISO 23894** (`iso-23894`) | AI risk management integrated with enterprise risk management — aligns to Solvency II ORSA |
| **NIST AI RMF** | Reference framework for US insurer AI governance; cited by NAIC Model Bulletin |
| **ISO 24027** (`iso-24027`) | Bias in insurance AI pricing — proxy discrimination technical assessment |

---

## High-Value Use Cases

### 1. Pricing and Underwriting AI — High-Risk Obligation Register
Automated underwriting and pricing AI for life, health, and motor insurance triggers EU AI Act Annex III high-risk obligations. The full Title III compliance burden applies: technical documentation, conformity assessment, logging, human oversight.

```sparql
# All high-risk obligations
# → ai/sparql/02-high-risk-obligations.rq  (filter: eu-ai-act)

# Stakeholder obligations: insurer as Deployer vs. AI vendor as Provider
# → ai/sparql/10-obligations-by-stakeholder.rq

# Human oversight — mandatory for individual coverage decisions
# → ai/sparql/A-03-ask-human-oversight-covered.rq

# Prohibited practices — check against prohibited uses of sensitive data categories
# → ai/sparql/06-prohibited-practices.rq
```

**Outcome:** Article-cited obligation register split by Provider/Deployer — foundation for AI governance programme and regulator engagement.

### 2. Proxy Discrimination Assessment in Pricing Models
Regulators (EIOPA, state commissioners, FCA) are increasingly scrutinising whether pricing AI uses proxy variables that correlate with protected characteristics. ISO 24027 provides the technical assessment framework.

```sparql
# Fairness controls across all frameworks
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Fairness)

# Bias and discrimination risks
# → ai/sparql/09-risks-by-category.rq  (filter: ai:Fairness)

# Assessment types required — what testing methodologies are prescribed?
# → ai/sparql/12-assessment-types.rq
```

**Outcome:** Structured fairness assessment programme with regulatory grounding — required for EIOPA and FCA AI Regulatory Strategy compliance.

### 3. Claims Automation — Explainability and Appeal Rights
Automated claims decisions at scale trigger GDPR Art. 22 rights (explanation, human review, contest). EU AI Act adds technical logging and monitoring obligations.

```sparql
# Explainability controls — what explanation must be provided?
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Explainability)

# Rights inventory — claimant rights to explanation and review
# → ai/sparql/07-rights-inventory.rq

# Lifecycle requirements — monitoring and post-deployment obligations
# → ai/sparql/05-requirements-by-lifecycle.rq  (filter: Monitor)
```

### 4. Solvency II ORSA + AI Risk Integration
Insurers must integrate AI model risk into Own Risk and Solvency Assessment. ISO 23894 provides the bridge between AI risk management and enterprise risk frameworks.

```sparql
# Risk register — AI risks structured for ORSA integration
# → ai/sparql/C-03-construct-risk-register.rq

# Risks by category — operational risk classification
# → ai/sparql/09-risks-by-category.rq

# Controls mapping — existing Solvency II controls vs. AI-specific gaps
# → ai/sparql/08-gap-analysis-dimensions.rq
```

### 5. Reinsurer / Capacity Provider Due Diligence
Reinsurers and Lloyd's syndicates increasingly require cedants and MGAs to demonstrate AI governance as a condition of capacity. IQ:NS generates the evidence pack.

```sparql
# Compliance profile — structured attestation
# → ai/sparql/C-01-construct-compliance-profile.rq

# Control coverage by dimension — demonstrate programme breadth
# → ai/sparql/03-controls-by-dimension.rq

# Assessment types completed — validation evidence
# → ai/sparql/12-assessment-types.rq
```

---

## Key Dimensions for Insurance AI

`ai:Fairness` · `ai:Explainability` · `ai:Transparency` · `ai:Accountability` · `ai:HumanOversight` · `ai:Robustness` · `ai:Privacy`

---

## Sector-Specific Graph Extensions Needed

| Gap | Priority |
|---|---|
| EIOPA AI Governance Guidelines (final) | High — binding on EU insurers; not yet mapped |
| NAIC Model Bulletin on AI (US) | High — adopted in multiple states; algorithmic pricing guidance |
| FCA AI Regulatory Strategy (UK) | High — senior manager accountability for AI decisions |
| Australian APRA AI risk guidance | Medium |
| Lloyd's of London AI minimum standards | Medium — required for delegated authority holders |

---

## Quick Wins

- **Regulator engagement pack:** `C-01-construct-compliance-profile.rq` → structured AI governance posture; table-ready for supervisor meetings
- **Actuarial working party report:** `03-controls-by-dimension.rq` (Fairness + Explainability) → control framework with ISO/EU citations
- **MGA capacity submission:** `12-assessment-types.rq` → evidence of validation activities for Lloyd's/reinsurer submissions
- **Board risk report:** `C-03-construct-risk-register.rq` → AI risk register integrated with Solvency II risk categories
