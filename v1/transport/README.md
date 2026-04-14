# IQ:NS — Transport & Autonomous Systems

Transport AI spans the broadest physical risk consequence of any sector: autonomous vehicles, AI in air traffic management, rail safety systems, and maritime navigation. EU AI Act Annex III point 2 explicitly lists AI safety components in road transport and critical infrastructure as high-risk. Simultaneously, sector-specific safety authorities (EASA, DVSA, IMO, ERA) are developing AI-specific rules that layer on top of the horizontal framework. The regulatory stack is uniquely deep and moving faster than any single framework document reflects.

---

## Who This Is For

| Persona | Pain Point |
|---|---|
| Autonomous Vehicle Programme Director | Navigating EU AI Act high-risk obligations, UN Regulation 157 type approval, and national AV legislation simultaneously |
| Aviation AI Systems Engineer | Aligning AI in flight systems to EASA AI Roadmap and EU AI Act without double-counting obligations |
| Rail Safety / Signalling Lead | Mapping AI in ETCS and train control systems to ERA guidance and EU AI Act |
| Head of Connected / Autonomous Mobility Policy | Advising transport authorities on AI governance frameworks for public deployment |
| Mobility-as-a-Service / Ride-Hail AI Lead | Managing AI dispatch, pricing, and safety systems under multiple overlapping regulatory regimes |

---

## Regulatory Surface

| Framework | Key Transport Exposure |
|---|---|
| **EU AI Act Annex III pt. 2** | AI safety components in road transport and critical infrastructure explicitly listed as high-risk — full Title III obligations apply |
| **EU AI Act Annex III pt. 1** | AI in biometric identification used in transport hubs — additional high-risk classification |
| **NIST AI RMF** | Referenced by US DOT and NHTSA in autonomous vehicle AI guidance |
| **ISO 23894** (`iso-23894`) | AI risk management — integrates with ISO 26262 (automotive functional safety) and IEC 61508 |
| **ISO 42001** | AI management system — required by EASA and ERA for AI system deployment approval |
| **MITRE ATLAS** (`mitre-atlas`) | Adversarial attack taxonomy — relevant for AI systems in connected and autonomous vehicles |
| **NIST AI 100-1** (`nist-ai-100-1`) | Robustness and adversarial ML — GPS spoofing, sensor adversarial attacks on AV perception |

---

## High-Value Use Cases

### 1. Autonomous Vehicle AI — High-Risk Obligation Register
Any AI safety component in road vehicles is high-risk under EU AI Act. This is additive to UN Regulation 155 (cybersecurity) and UN Regulation 157 (ALKS type approval). The obligation stack is the most complex in the transport sector.

```sparql
# All high-risk obligations
# → ai/sparql/02-high-risk-obligations.rq  (filter: eu-ai-act)

# Prohibited practices — confirm no prohibited biometric or manipulation use
# → ai/sparql/06-prohibited-practices.rq

# Human oversight controls — mandatory; driver/operator override requirements
# → ai/sparql/A-03-ask-human-oversight-covered.rq

# Safety controls
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Safety)

# Stakeholder obligations: OEM (Provider) vs. fleet operator (Deployer)
# → ai/sparql/10-obligations-by-stakeholder.rq
```

**Outcome:** Unified obligation register across EU AI Act + UN Regulation 157 + ISO 23894 — eliminates redundant compliance workstreams across type approval and AI governance teams.

### 2. EASA AI Roadmap Alignment
EASA's AI Roadmap 2.0 establishes a trustworthiness framework for AI in civil aviation. It is structured around similar dimensions to IQ:NS and maps to EU AI Act obligations — but uses different terminology. IQ:NS provides the semantic bridge.

```sparql
# Cross-framework equivalents — EASA concepts vs. EU AI Act vs. ISO 42001
# → ai/sparql/04-cross-framework-equivalents.rq

# Gap analysis — EASA Roadmap vs. full EU AI Act obligation set
# → ai/sparql/08-gap-analysis-dimensions.rq

# Reliability and Safety controls — EASA's primary concern
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Reliability, ai:Safety)
```

**Outcome:** Unified AI governance framework satisfying EASA, EU AI Act, and ISO 42001 simultaneously — required for EASA AI system certification pathway approval.

### 3. Adversarial Robustness in Connected Vehicles
Connected and autonomous vehicles face adversarial attacks: sensor spoofing, adversarial patches on road signs, model poisoning through OTA updates. MITRE ATLAS and NIST AI 100-1 provide the threat taxonomy.

```sparql
# Security and robustness risks
# → ai/sparql/09-risks-by-category.rq  (filter: ai:Security, ai:Robustness)

# Robustness controls across MITRE ATLAS + NIST AI 100-1
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Robustness)

# Construct risk register for type approval documentation
# → ai/sparql/C-03-construct-risk-register.rq
```

### 4. Rail AI Safety Assurance
AI in train protection systems (ETCS, ATP) and timetable optimisation must meet ERA Technical Specifications for Interoperability and EU AI Act simultaneously. Safety assurance must be documented across the full lifecycle.

```sparql
# Lifecycle requirements — design through post-deployment monitoring
# → ai/sparql/05-requirements-by-lifecycle.rq

# Assessment types — what validation activities are required?
# → ai/sparql/12-assessment-types.rq

# Is human oversight maintained at all times?
# → ai/sparql/A-03-ask-human-oversight-covered.rq
```

### 5. Mobility-as-a-Service Platform AI Governance
Ride-hail and MaaS platforms deploy AI for dispatch, dynamic pricing, driver monitoring, and safety scoring — each triggering distinct obligation sets. Dynamic pricing AI may also be high-risk (affects access to essential services).

```sparql
# High-risk determination for pricing / dispatch AI
# → ai/sparql/A-01-ask-high-risk-controlled.rq

# Fairness controls — non-discriminatory dispatch and pricing
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Fairness)

# Transparency to drivers and passengers — mandatory disclosure
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Transparency)
```

---

## Key Dimensions for Transport AI

`ai:Safety` · `ai:Robustness` · `ai:Reliability` · `ai:HumanOversight` · `ai:Transparency` · `ai:Accountability` · `ai:Security`

---

## Sector-Specific Graph Extensions Needed

| Gap | Priority |
|---|---|
| EASA AI Roadmap 2.0 trustworthiness objectives as ai:Requirements | High — aviation AI certification pathway not mapped |
| UN Regulation 157 (ALKS) AI-specific obligations | High — type approval requirements not mapped |
| ERA (European Union Agency for Railways) AI guidelines | High — rail sector AI governance emerging |
| UK DVSA Connected & Automated Vehicles legislation | Medium — UK Automated Vehicles Act 2024 obligations |
| IMO Maritime AI guidance | Medium — autonomous shipping obligations developing |
| ISO 26262 × EU AI Act intersection (automotive functional safety) | Medium — critical for OEM compliance engineers |

---

## Quick Wins

- **Type approval AI annex:** `C-01-construct-compliance-profile.rq` → structured compliance attestation for homologation authorities
- **Functional safety bridge:** `04-cross-framework-equivalents.rq` → map ISO 26262 / IEC 61508 controls to EU AI Act obligations
- **Board safety committee:** `C-03-construct-risk-register.rq` → AI risk register for transport system portfolio
- **Regulator engagement (EASA / ERA / DVSA):** `14-principles-catalogue.rq` + `03-controls-by-dimension.rq` → structured AI governance posture for regulatory dialogue
