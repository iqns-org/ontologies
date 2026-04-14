# IQ:NS — Energy & Critical Infrastructure

AI systems operating within energy grids, water networks, transport infrastructure, and other critical systems face the highest safety consequences of any deployment context — and the most complex regulatory intersection. NIS2 (operational resilience), EU AI Act (safety-critical high-risk), DORA (financial critical infrastructure), sector-specific safety standards, and national critical infrastructure protection regimes all apply simultaneously. No framework covers this crosswalk; IQ:NS does.

---

## Who This Is For

| Persona | Pain Point |
|---|---|
| CISO / OT Security Lead | Mapping AI system security obligations under NIS2 and EU AI Act against existing ICS/SCADA governance |
| Head of Grid / Network Digitalisation | Deploying AI for demand forecasting, fault detection, and grid optimisation under the EU AI Act safety framework |
| Regulatory Affairs / Ofgem / ACER Reporting | Demonstrating AI governance to energy regulators across multiple jurisdictions |
| Chief Safety Officer | Integrating AI model risk into existing functional safety management systems (IEC 61511, IEC 61508) |
| AI / Data Science Lead (Utilities) | Understanding which technical obligations apply to predictive maintenance and asset management AI |

---

## Regulatory Surface

| Framework | Key Energy Exposure |
|---|---|
| **EU AI Act Annex III pt. 2** | AI safety components in critical infrastructure (energy, water, transport) explicitly listed as high-risk — full Title III applies |
| **NIS2 Directive** | Energy operators are essential entities under NIS2; AI systems in OT environments trigger cybersecurity incident reporting and supply-chain risk obligations |
| **ISO 42001** | AI management system — increasingly required by TSOs and DSOs as condition of third-party AI deployment |
| **NIST AI RMF** | Reference for US utility AI governance; cited by NERC and DOE guidance |
| **ISO 23894** (`iso-23894`) | AI risk management integrated with enterprise risk — aligns to energy sector ERM and functional safety |
| **NIST AI 100-1** (`nist-ai-100-1`) | Adversarial ML threats — directly relevant to AI systems controlling physical infrastructure |
| **MITRE ATLAS** (`mitre-atlas`) | Attack taxonomy for AI systems in critical infrastructure — red-team baseline |

---

## High-Value Use Cases

### 1. Grid AI Safety Classification and Obligation Register
AI systems that autonomously control or materially influence power grid operations are high-risk under EU AI Act Annex III. Combined with IEC 61511 functional safety requirements, the governance obligation is dense.

```sparql
# High-risk obligations — mandatory for safety-critical infrastructure AI
# → ai/sparql/02-high-risk-obligations.rq  (filter: eu-ai-act)

# Prohibited practices — no AI that creates unacceptable safety risk
# → ai/sparql/06-prohibited-practices.rq

# Human oversight — mandatory; automated control must have human fallback
# → ai/sparql/A-03-ask-human-oversight-covered.rq

# Safety controls — full cross-framework control set
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Safety)
```

**Outcome:** Safety-grounded obligation register that bridges EU AI Act and functional safety standards — required for grid operator board approval and regulatory filing.

### 2. OT/AI Cybersecurity Threat Modelling
AI systems in operational technology environments (SCADA, DCS) face a unique threat surface: adversarial attacks can cause physical consequences. MITRE ATLAS and NIST AI 100-1 provide the attack taxonomy.

```sparql
# Security risks — AI-specific attacks on infrastructure
# → ai/sparql/09-risks-by-category.rq  (filter: ai:Security)

# Security controls across MITRE ATLAS, NIST AI 100-1
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Security)

# Robustness controls — adversarial robustness requirements
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Robustness)
```

**Outcome:** AI-specific OT threat model with cross-framework controls — feeds directly into NIS2 cybersecurity risk management measures documentation.

### 3. Predictive Maintenance and Asset Management AI
AI for turbine, transformer, and asset condition monitoring is high-value but must meet reliability and explainability obligations — particularly when maintenance decisions affect grid stability.

```sparql
# Reliability controls — what accuracy and availability obligations apply?
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Reliability)

# Lifecycle requirements — validation and monitoring in production
# → ai/sparql/05-requirements-by-lifecycle.rq

# Risk register — asset management AI risks
# → ai/sparql/C-03-construct-risk-register.rq
```

### 4. Third-Party AI Vendor Risk (NIS2 Supply Chain)
NIS2 Art. 21 requires essential entities to assess AI vendor cybersecurity practices. This combines with EU AI Act deployer obligations — the energy operator is responsible regardless of where the AI was built.

```sparql
# Controls by dimension — vendor assessment criteria grounded in regulation
# → ai/sparql/03-controls-by-dimension.rq

# Assessment types — what validation must the vendor demonstrate?
# → ai/sparql/12-assessment-types.rq

# Cross-framework equivalents — does vendor's ISO certification satisfy NIS2?
# → ai/sparql/04-cross-framework-equivalents.rq
```

### 5. Sustainability and Scope 3 AI Obligations
EU Corporate Sustainability Reporting Directive (CSRD) requires disclosure of AI system environmental impact. GovGraph's `ai:Sustainability` dimension captures cross-framework energy and environmental obligations.

```sparql
# Sustainability controls
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Sustainability)

# Principles related to sustainability
# → ai/sparql/14-principles-catalogue.rq
```

---

## Key Dimensions for Energy AI

`ai:Safety` · `ai:Security` · `ai:Robustness` · `ai:Reliability` · `ai:Accountability` · `ai:HumanOversight` · `ai:Sustainability`

---

## Sector-Specific Graph Extensions Needed

| Gap | Priority |
|---|---|
| NIS2 AI-specific obligations as ai:Requirements | High — essential entity obligations not yet mapped  |
| NERC CIP AI cyber standards (US) | High — grid cybersecurity AI requirements |
| Ofgem AI governance expectations (UK) | High — published 2025; energy licence conditions |
| IEC 62443 OT cybersecurity × AI intersection | Medium — foundational reference for industrial AI security |
| EU Electricity Market Design AI disclosure requirements | Medium — emerging post-REMIT AI trading obligations |
| CSRD AI environmental impact reporting | Medium — Scope 3 AI emissions disclosure |

---

## Quick Wins

- **Board safety committee:** `C-03-construct-risk-register.rq` → AI risk register aligned to enterprise risk framework
- **NIS2 cybersecurity report:** `03-controls-by-dimension.rq` (Security + Robustness) → control evidence for incident reporting capability
- **Regulator engagement pack:** `C-01-construct-compliance-profile.rq` → AI governance posture for Ofgem/ACER/FERC
- **Procurement assessment:** `12-assessment-types.rq` → validation evidence requirements; embed in AI supplier contracts
