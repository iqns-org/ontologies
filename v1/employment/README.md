# IQ:NS — Employment & HR

AI systems used in recruitment, workforce management, performance evaluation, and worker monitoring are among the most litigation-exposed categories under EU AI Act Annex III (point 4). They intersect labour law, employment discrimination law, GDPR, and sector-specific obligations — a crosswalk that no individual framework document maps completely. IQ:NS connects them.

---

## Who This Is For

| Persona | Pain Point |
|---|---|
| CHRO / Head of People Analytics | Deploying AI-assisted hiring or performance tools without triggering discrimination claims or regulatory enforcement |
| Employment Counsel | Advising on AI system obligations before deployment, not after a complaint |
| HR Technology Vendor | Demonstrating compliance to enterprise clients who are themselves regulated |
| Works Council / Labour Representative | Understanding what oversight rights workers have over AI-based decisions |
| Internal Audit | Assessing AI systems used in workforce decisions against all applicable frameworks |

---

## Regulatory Surface

| Framework | Key Employment Exposure |
|---|---|
| **EU AI Act Annex III pt. 4** | AI for recruitment, selection, promotion, termination, task allocation, and performance monitoring all explicitly listed as high-risk — full Title III obligations apply |
| **EU GDPR AI** (`eu-gdpr-ai`) | Art. 22 automated decision-making applies to employment decisions; Art. 9 special category data (union membership, health) at risk |
| **ISO 24027** (`iso-24027`) | Bias in AI and ML decision systems — the technical standard underpinning discrimination risk assessment |
| **NIST AI RMF** | Fairness and bias controls — increasingly cited in US EEOC AI guidance |
| **IEEE 7000** | Ethical impact assessment — required by some large enterprise and unionised employer procurement standards |
| **PAI Guidelines** | Responsible practices for worker-facing AI — referenced in collective bargaining frameworks |

---

## High-Value Use Cases

### 1. Recruitment AI High-Risk Classification and Obligation Register
Any AI system that filters, ranks, or scores job candidates is high-risk under EU AI Act Annex III. The obligation set is dense: technical documentation, conformity assessment, human oversight, logging, transparency to candidates.

```sparql
# All high-risk obligations — mandatory for Annex III pt. 4 systems
# → ai/sparql/02-high-risk-obligations.rq  (filter: eu-ai-act)

# Prohibited practices — check for prohibited subliminal manipulation or exploitation
# → ai/sparql/06-prohibited-practices.rq

# Human oversight — mandatory; must be documented
# → ai/sparql/A-03-ask-human-oversight-covered.rq

# Stakeholder obligations: Provider (vendor) vs. Deployer (employer)
# → ai/sparql/10-obligations-by-stakeholder.rq
```

**Outcome:** Complete obligation register split by vendor vs. employer responsibility — essential for contract drafting and board sign-off.

### 2. Algorithmic Bias and Discrimination Risk Assessment
EEOC (US), EHRC (UK), and EU national equality bodies are actively investigating AI hiring tools. ISO 24027 provides the technical framework for bias assessment.

```sparql
# Fairness controls — all frameworks
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Fairness)

# Fairness risks — bias, discrimination, disparate impact
# → ai/sparql/09-risks-by-category.rq  (filter: ai:Fairness)

# ISO 24027 bias assessment requirements specifically
# → ai/sparql/12-assessment-types.rq
```

**Outcome:** Structured bias audit framework with regulatory grounding — defensible before an equality regulator.

### 3. Worker Monitoring and Surveillance AI
Email monitoring, productivity tracking, location surveillance, and sentiment analysis tools applied to workers trigger GDPR, EU AI Act, and national works council consultation requirements.

```sparql
# Privacy controls — what data protection obligations apply?
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Privacy)

# Transparency rights — workers' right to know what AI collects about them
# → ai/sparql/07-rights-inventory.rq

# Human oversight — decision review rights
# → ai/sparql/A-03-ask-human-oversight-covered.rq
```

### 4. HR Vendor Due Diligence
Enterprises deploying third-party HR AI (ATS platforms, performance management tools, engagement survey AI) are the **Deployer** under EU AI Act — they inherit obligations regardless of where the AI was built.

```sparql
# Controls by dimension — generate vendor questionnaire
# → ai/sparql/03-controls-by-dimension.rq

# Cross-framework equivalents — does vendor's ISO 42001 cover EU AI Act deployer obligations?
# → ai/sparql/04-cross-framework-equivalents.rq

# Gap analysis — what deployer obligations remain uncovered
# → ai/sparql/08-gap-analysis-dimensions.rq
```

---

## Key Dimensions for Employment AI

`ai:Fairness` · `ai:Transparency` · `ai:HumanOversight` · `ai:Accountability` · `ai:Privacy` · `ai:Explainability`

---

## Sector-Specific Graph Extensions Needed

| Gap | Priority |
|---|---|
| US EEOC AI Guidelines (2024) | High — specific technical standards for adverse impact testing |
| NYC Local Law 144 (automated employment decision tools) | High — first jurisdiction-level audit requirement; model for others |
| EU Platform Work Directive AI provisions | High — algorithmic management obligations for gig workers |
| UK ICO Employment Guidance on AI | Medium |
| Works Council consultation obligations (Germany BetrVG §87) | Medium — co-determination rights for AI deployment |

---

## Quick Wins

- **Candidate transparency notice:** `07-rights-inventory.rq` → structured list of rights to disclose in AI-assisted hiring
- **Board HR committee:** `C-03-construct-risk-register.rq` filtered to employment AI systems → board-ready risk register
- **Vendor contract schedule:** `10-obligations-by-stakeholder.rq` → split Provider/Deployer obligations for contract drafting
- **Bias audit report:** `03-controls-by-dimension.rq` (Fairness) + `12-assessment-types.rq` → audit programme with ISO 24027 citations
