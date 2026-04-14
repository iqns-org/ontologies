# IQ:NS — Government & Public Sector

Governments are simultaneously the **authors** of AI regulation and its most scrutinised implementers. Public sector AI deployments face the highest political and legal accountability of any sector: judicial review, freedom-of-information obligations, human rights constraints, and procurement rules that require demonstrable compliance before deployment. IQ:NS turns the regulatory frameworks that governments wrote into the tools governments need to govern themselves.

---

## Who This Is For

| Persona | Pain Point |
|---|---|
| Central AI Policy Unit | Mapping national AI strategy obligations to concrete agency-level implementation requirements |
| Procurement / Digital Transformation Officer | Assessing AI vendor compliance before contract award |
| Chief Data Officer | Navigating data governance obligations across GDPR, sector rules, and freedom-of-information law |
| Constitutional / Administrative Lawyer | Grounding AI decision-making in human rights and due process obligations |
| Parliamentary / Congressional Oversight Staff | Auditing agency AI deployments against legislative intent |

---

## Regulatory Surface

| Framework | Key Government Exposure |
|---|---|
| **EU AI Act** | Public sector deployers face mandatory fundamental rights impact assessments (Art. 27); law enforcement AI is the most restricted category (Annex III pt. 6–7, some prohibited) |
| **UNESCO AI Ethics** (`unesco-ai`) | Adopted by 193 member states; procurement reference in non-EU jurisdictions |
| **OECD AI Principles** (`oecd-ai`) | Baseline for G7/G20 AI governance commitments — referenced in national strategies |
| **Singapore AI Gov v2** (`sg-ai-gov-v2`) | Model governance framework for government agencies — one of the most operationally detailed |
| **Canada DCDD** (`canada-dcdd`) | Directive on Automated Decision-Making — binding on Canadian federal agencies, model for others |
| **Executive Order 14110** (`eo-14110`) | US federal agency AI safety and security requirements |
| **NIST AI RMF** | OMB M-24-10 mandates NIST AI RMF adoption across US federal agencies |
| **ISO 42001** | Certification pathway referenced in UK AI procurement standards and EU public procurement guidance |

---

## High-Value Use Cases

### 1. Fundamental Rights Impact Assessment (FRIA)
EU AI Act Art. 27 requires public sector bodies deploying high-risk AI to conduct a FRIA before deployment. This is the most burdensome new obligation for government AI teams.

```sparql
# All high-risk obligations — mandatory starting point
# → ai/sparql/02-high-risk-obligations.rq  (filter: eu-ai-act)

# Rights inventory — what rights must be protected?
# → ai/sparql/07-rights-inventory.rq

# Human oversight requirements — mandatory for public sector high-risk
# → ai/sparql/A-03-ask-human-oversight-covered.rq

# Assessment types required before deployment
# → ai/sparql/12-assessment-types.rq
```

**Outcome:** Structured FRIA template with article citations, grounding rights obligations in specific framework provisions — defensible before a supervisory authority or court.

### 2. Prohibited Practices Clearance
Before deploying any AI system, public bodies must confirm it is not categorically prohibited. Social scoring by public authorities and most real-time remote biometric identification are banned under EU AI Act Art. 5.

```sparql
# Prohibited practices — mandatory pre-deployment check
# → ai/sparql/06-prohibited-practices.rq

# Boolean: is the system prohibited?
# → ai/sparql/A-02-ask-prohibited-practices-present.rq
```

**Outcome:** Documented clearance memo with article citations — essential for legal sign-off and ministerial accountability.

### 3. AI Procurement Vendor Assessment
Government procurement rules increasingly require vendors to demonstrate AI compliance. IQ:NS generates the assessment criteria automatically.

```sparql
# Full control set across all dimensions — use as vendor questionnaire
# → ai/sparql/03-controls-by-dimension.rq

# Cross-framework coverage — does vendor's ISO 42001 cert satisfy EU AI Act?
# → ai/sparql/04-cross-framework-equivalents.rq

# Gap analysis — what obligations remain uncovered by vendor's certifications?
# → ai/sparql/08-gap-analysis-dimensions.rq
```

**Outcome:** Structured vendor due diligence framework aligned to actual regulatory obligations — defensible against judicial review of procurement decisions.

### 4. National AI Strategy Implementation Mapping
Governments adopting OECD/UNESCO AI principles must translate high-level commitments into agency-level obligations. IQ:NS maps the full chain: principle → requirement → control → lifecycle stage.

```sparql
# Principles catalogue — all principles across frameworks
# → ai/sparql/14-principles-catalogue.rq

# Requirements by lifecycle — what must happen at each stage?
# → ai/sparql/05-requirements-by-lifecycle.rq

# Stakeholder obligations — which agency / role is responsible?
# → ai/sparql/10-obligations-by-stakeholder.rq
```

### 5. Cross-Jurisdiction Alignment (Federal + State/Provincial + EU)
Government agencies operating internationally or managing EU-origin data face layered obligations: EO 14110 + NIST AI RMF + EU AI Act + GDPR simultaneously.

```sparql
# Framework inventory — all relevant frameworks in scope
# → ai/sparql/01-framework-inventory.rq

# Cross-framework equivalents — find where obligations overlap
# → ai/sparql/04-cross-framework-equivalents.rq

# Construct alignment graph — full obligation crosswalk
# → ai/sparql/C-02-construct-alignment-graph.rq
```

---

## Key Dimensions for Government AI

`ai:Accountability` · `ai:Transparency` · `ai:HumanOversight` · `ai:Fairness` · `ai:Safety` · `ai:Privacy` · `ai:Explainability`

---

## Sector-Specific Graph Extensions Needed

| Gap | Priority |
|---|---|
| EU AI Act Art. 27 FRIA procedural requirements | High — not yet fully modelled as ai:Assessment subclass |
| Canada DCDD Directive Levels 1–4 (automated decision impact) | High — excellent template for other jurisdictions |
| UK AI Regulation Bill (when enacted) | High — principles-based regime, different structure |
| Australia AI Ethics Framework | Medium — government-adopted, OECD-aligned |
| US OMB M-24-10 federal agency AI requirements | Medium — detailed agency-level obligations |
| Open Government / FOI obligations for AI decisions | Medium — not yet modelled in any framework |

---

## Quick Wins

- **Ministerial briefing:** `C-01-construct-compliance-profile.rq` → compliance posture of a specific AI system in minutes
- **Parliamentary accountability:** `10-obligations-by-stakeholder.rq` → RACI matrix for who is accountable for each obligation
- **Audit committee pack:** `C-03-construct-risk-register.rq` → structured risk register with source citations
- **Policy equivalence analysis:** `04-cross-framework-equivalents.rq` → show G7 AI Code of Conduct alignment to domestic obligations
