# IQ:NS — Public Safety & Law Enforcement

Law enforcement and public safety AI sits at the apex of EU AI Act regulatory restriction. Biometric identification in public spaces, predictive policing, social scoring, and AI-assisted criminal justice decisions are either categorically prohibited (Art. 5) or subject to the strictest high-risk obligations (Annex III pt. 6–7) of any category in the Act. The compliance challenge is not optional or gradual — these obligations are in force, enforcement is active, and the consequences of non-compliance include market withdrawal, fines up to €35M, and criminal accountability for responsible officers.

---

## Who This Is For

| Persona | Pain Point |
|---|---|
| Chief Constable / Commissioner / Police Technology Lead | Determining which AI tools are legally deployable and which are prohibited before procurement |
| Government AI Policy Unit | Advising on the narrow lawful use cases for law enforcement AI under EU AI Act and ECHR |
| Civil Liberties / Human Rights Unit (within agencies) | Documenting rights protection measures to pre-empt legal challenge |
| Procurement / Commercial (Police Forces / Border Agencies) | Assessing AI vendor compliance before contract award — the contracting authority carries liability |
| AI Vendor to Law Enforcement | Understanding which products can legally be sold to EU law enforcement bodies |

---

## Regulatory Surface

| Framework | Key Public Safety Exposure |
|---|---|
| **EU AI Act Art. 5** | Categorical prohibitions directly affecting law enforcement: real-time remote biometric identification in public spaces (with narrow exceptions); predictive policing based solely on profiling; AI inferring political opinion, race, sexual orientation; social scoring |
| **EU AI Act Annex III pt. 6–7** | AI for law enforcement (crime risk assessment, evidence reliability, criminal profiling, polygraphs) and migration/asylum decisions listed as high-risk — strictest Title III obligations |
| **EU GDPR AI** (`eu-gdpr-ai`) | Law Enforcement Directive (LED) applies rather than GDPR for police processing — different legal basis requirements |
| **EU Charter / ECHR** | Art. 8 (privacy), Art. 6 (fair trial), Art. 14 (non-discrimination) — constitutional floor beneath all AI obligations |
| **UNESCO AI Ethics** (`unesco-ai`) | Human rights-based approach explicitly required — referenced in oversight body guidance |
| **NIST AI RMF** | Fairness, bias, and robustness controls — referenced in US DOJ AI guidance and FBI AI framework |
| **ISO 24027** (`iso-24027`) | Bias assessment — mandatory for any AI system affecting criminal justice decisions |
| **MITRE ATLAS** (`mitre-atlas`) | Adversarial attacks on law enforcement AI — critical for counter-adversary scenarios |

---

## High-Value Use Cases

### 1. Pre-Procurement Prohibited Practices Clearance — Mandatory
Before procuring any AI tool for law enforcement use, the contracting authority must confirm the system is not categorically prohibited under Art. 5. This is a hard legal gate — not a risk assessment.

```sparql
# Prohibited practices — mandatory first check; no exceptions without Art. 5 criteria
# → ai/sparql/06-prohibited-practices.rq

# Boolean first-pass: is this system in a prohibited category?
# → ai/sparql/A-02-ask-prohibited-practices-present.rq
```

**Outcome:** Legally documented clearance memo — required before procurement, essential for ministerial/commissioner authorisation, and the first document a court will ask for in a legal challenge.

### 2. High-Risk AI Obligation Register for Law Enforcement
For AI that passes the prohibition check, Annex III pt. 6 applies: crime risk assessment tools, AI-assisted investigative decision support, forensic analysis AI, and border control all require the full Title III compliance apparatus.

```sparql
# All high-risk obligations — the full Title III burden
# → ai/sparql/02-high-risk-obligations.rq  (filter: eu-ai-act)

# Human oversight — mandatory; no fully automated criminal justice AI decisions
# → ai/sparql/A-03-ask-human-oversight-covered.rq

# Stakeholder obligations — law enforcement body as Deployer
# → ai/sparql/10-obligations-by-stakeholder.rq

# Assessment types — what conformity assessment is required?
# → ai/sparql/12-assessment-types.rq
```

**Outcome:** Structured obligation register for procurement documentation — maps Art. 43 conformity assessment requirements and establishes the accountability chain from CJEU through to operational officers.

### 3. Biometric AI — Lawful Use Mapping
Real-time remote biometric identification (RRBI) in public spaces is prohibited except under three narrow Art. 5(2) exceptions: targeted search for specific victims, prevention of specific imminent terrorist threat, or apprehension of specific serious crime suspects. Each exception requires prior judicial or independent administrative authorisation.

```sparql
# Prohibited practices — biometric identification specifics
# → ai/sparql/06-prohibited-practices.rq

# Rights inventory — data subjects' rights in biometric processing
# → ai/sparql/07-rights-inventory.rq

# Human oversight — mandatory prior authorisation requirement
# → ai/sparql/A-03-ask-human-oversight-covered.rq
```

**Outcome:** Legal framework memo documenting the narrow lawful use corridor — required for any facial recognition or biometric surveillance deployment.

### 4. Algorithmic Bias in Criminal Justice AI
Predictive risk assessment, recidivism scoring, and crime mapping AI carry evidence of racial and socioeconomic bias documented across US and European deployments. Regulators and courts are increasingly treating unexplained bias as an Art. 5 prohibited practice or Annex III high-risk obligation breach.

```sparql
# Fairness risks and controls
# → ai/sparql/09-risks-by-category.rq  (filter: ai:Fairness)
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Fairness)

# Bias assessment requirements (ISO 24027)
# → ai/sparql/12-assessment-types.rq

# Explainability — right to explanation for adverse decisions
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Explainability)
```

**Outcome:** Structured algorithmic impact assessment programme grounded in ISO 24027 and EU AI Act — defensible before supervisory authority, court, or parliamentary inquiry.

### 5. Border Control and Migration AI
AI in asylum processing, border crossing assessment, and migration decision support is high-risk under Annex III pt. 7. Given the fundamental rights stakes, oversight requirements are among the strictest in the Act.

```sparql
# High-risk obligations for migration AI
# → ai/sparql/02-high-risk-obligations.rq

# Rights inventory — asylum seeker and migrant rights under EU AI Act and Charter
# → ai/sparql/07-rights-inventory.rq

# Human oversight — mandatory for all asylum and migration decisions
# → ai/sparql/A-03-ask-human-oversight-covered.rq

# Fairness controls — non-discrimination in border AI
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Fairness)
```

---

## Key Dimensions for Public Safety AI

`ai:HumanOversight` · `ai:Accountability` · `ai:Fairness` · `ai:Transparency` · `ai:Explainability` · `ai:Safety` · `ai:Privacy`

---

## Sector-Specific Graph Extensions Needed

| Gap | Priority |
|---|---|
| EU AI Act Art. 5 exceptions (Art. 5(2)–(5)) as structured conditions | Critical — the lawful use corridor for RRBI is not yet modelled as conditional ai:Permissions |
| Law Enforcement Directive (LED) AI obligations | High — different legal basis from GDPR; not yet mapped |
| EU Agency for Fundamental Rights (FRA) AI law enforcement guidance | High — operational guidance for national forces |
| Interpol AI guidelines for international law enforcement | Medium |
| UK Surveillance Camera Code of Practice × AI | Medium — biometric surveillance in UK public space |
| US DOJ AI policy for federal law enforcement | Medium — FBI, DEA, DHS AI governance requirements |

---

## Quick Wins

- **Commissioner authorisation pack:** `06-prohibited-practices.rq` + `A-02-ask-prohibited-practices-present.rq` → 2-page legal clearance document before any biometric AI deployment
- **Parliamentary accountability brief:** `10-obligations-by-stakeholder.rq` → RACI matrix for ministerial accountability
- **Procurement legal gateway:** `02-high-risk-obligations.rq` + `12-assessment-types.rq` → conformity assessment checklist for AI vendor contracts
- **Community oversight submission:** `07-rights-inventory.rq` + `03-controls-by-dimension.rq` (Fairness) → structured rights impact statement for police oversight boards
