# IQ:NS — Defence & Dual-Use

Defence AI operates in the regulatory vacuum between the world's most consequential deployment context and the most fragmented governance landscape. The EU AI Act explicitly excludes military and national security applications (Art. 2(3)) — but this exclusion is narrower than it appears. Defence primes exporting AI systems, dual-use technology companies, and NATO member state procurement all face distinct and rapidly crystallising obligations. The International Humanitarian Law (IHL) autonomy constraints, US DoD AI Ethics Principles, and export control regimes create a compliance surface that no existing governance document maps completely.

---

## Who This Is For

| Persona | Pain Point |
|---|---|
| Defence Prime AI / Systems Engineering Lead | Navigating DoD AI Ethics Principles, ITAR/EAR export controls, and NATO DIANA requirements simultaneously |
| Dual-Use Technology Counsel | Determining where the EU AI Act military exclusion ends and civilian deployment obligations begin |
| Chief AI Responsible Officer (DoD / allied MoD) | Implementing Responsible AI adoption mandates across complex acquisition programmes |
| Defence Export Compliance | Managing AI technology transfer obligations under ITAR, EAR, and UK Export Control Order |
| NATO / Allied Nation Policy Advisor | Harmonising national Responsible AI in Defence principles across alliance AI interoperability |

---

## Regulatory Surface

| Framework | Key Defence Exposure |
|---|---|
| **US DoD AI Ethics Principles (2020)** | Binding on US DoD AI acquisition — Responsible, Equitable, Traceable, Reliable, Governable |
| **EU AI Act Art. 2(3)** | Military/national security exclusion — but narrow: commercial AI used in defence missions may still be in scope during development and testing phases |
| **NIST AI RMF** | Referenced in DoD Responsible AI implementation path; CDAO adoption framework |
| **OECD AI Principles** | G7 nations aligned; referenced in NATO AI principles for allies |
| **UNESCO AI Ethics** | Invoked in IHL discussions on autonomous weapons — soft law shaping treaty negotiations |
| **MITRE ATLAS** (`mitre-atlas`) | Adversarial ML attack taxonomy — essential for threat modelling military AI systems |
| **NIST AI 100-1** (`nist-ai-100-1`) | Adversarial robustness baseline — particularly relevant to AI in contested electromagnetic environments |
| **Google SAIF** (`google-saif`) | Supply-chain AI security — relevant to dual-use commercial components in defence systems |

---

## High-Value Use Cases

### 1. Dual-Use Technology Boundary Analysis
The EU AI Act military exclusion (Art. 2(3)) does not cover: AI developed commercially and then applied to military use; AI used in both civilian and military contexts; and AI in defence supply chains that also serve civilian markets. Mapping the boundary is the first step.

```sparql
# Framework inventory — understand which frameworks apply to dual-use scenarios
# → ai/sparql/01-framework-inventory.rq

# Prohibited practices — what EU AI Act prohibitions survive the military exclusion?
# → ai/sparql/06-prohibited-practices.rq

# Stakeholder obligations — developer vs. integrator vs. operator roles
# → ai/sparql/10-obligations-by-stakeholder.rq
```

**Outcome:** Structured legal analysis of where EU AI Act obligations attach to dual-use AI development — essential before technology transfer or export.

### 2. DoD Responsible AI (RAI) Implementation Mapping
US DoD Directive 3000.09 and the CDAO Responsible AI adoption framework require contractor and programme office AI governance aligned to the five DoD AI Ethics Principles. IQ:NS maps these to the broader multi-lateral framework landscape.

```sparql
# Cross-framework equivalents — DoD RAI principles vs. OECD/NIST/NATO
# → ai/sparql/04-cross-framework-equivalents.rq

# Controls by dimension — Reliability and Governability (traceability, human oversight)
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Reliability, ai:HumanOversight)

# Human oversight controls — LOAC compliance requires meaningful human control
# → ai/sparql/A-03-ask-human-oversight-covered.rq
```

**Outcome:** Unified control framework satisfying DoD RAI, NATO AI principles, and OECD AI principles simultaneously — eliminates redundant parallel compliance workstreams across alliance partners.

### 3. Adversarial AI Threat Modelling for Military Systems
AI systems operating in contested environments face adversarial attacks that have no civilian equivalent: adversarial patches on targets, model poisoning through training data supply chain, GPS spoofing feeding into AI sensor fusion. MITRE ATLAS provides the taxonomy.

```sparql
# Security risks — adversarial ML attack catalogue
# → ai/sparql/09-risks-by-category.rq  (filter: ai:Security)

# Robustness controls — adversarial robustness requirements
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Robustness, ai:Security)

# Construct alignment graph — risk-to-control mapping
# → ai/sparql/C-02-construct-alignment-graph.rq
```

**Outcome:** Structured adversarial threat model with MITRE ATLAS and NIST AI 100-1 citations — required for programme protection plans and RMF A&A packages.

### 4. NATO AI Interoperability Compliance
NATO's Principles of Responsible Use of AI in Defence (2021) and DIANA AI programme requirements create new obligations for allied nation defence acquisition that must harmonise across member states.

```sparql
# Principles catalogue — map NATO principles to multi-framework equivalents
# → ai/sparql/14-principles-catalogue.rq

# Gap analysis — member state implementation vs. NATO baseline
# → ai/sparql/08-gap-analysis-dimensions.rq

# Cross-framework alignment — where OECD/UNESCO principles = NATO principles
# → ai/sparql/04-cross-framework-equivalents.rq
```

### 5. International Humanitarian Law (IHL) Meaningful Human Control
The ICRC and CCW negotiations on Lethal Autonomous Weapons Systems (LAWS) centre on meaningful human control as the key legal constraint. This maps directly to `ai:HumanOversight` across IQ:NS frameworks.

```sparql
# Human oversight controls — the IHL compliance baseline
# → ai/sparql/A-03-ask-human-oversight-covered.rq
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:HumanOversight)

# Accountability controls — who is accountable for autonomous AI actions?
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Accountability)

# Rights inventory — IHL protected persons' rights
# → ai/sparql/07-rights-inventory.rq
```

---

## Key Dimensions for Defence AI

`ai:HumanOversight` · `ai:Reliability` · `ai:Robustness` · `ai:Security` · `ai:Accountability` · `ai:Safety` · `ai:Transparency`

---

## Sector-Specific Graph Extensions Needed

| Gap | Priority |
|---|---|
| US DoD AI Ethics Principles as ai:Principles | High — five principles not yet mapped as named graph entities |
| NATO Responsible AI in Defence Principles | High — 2021 document; increasingly referenced in allied procurement |
| DoD Directive 3000.09 (Autonomous Weapons) | High — meaningful human control requirements |
| ITAR/EAR AI technology transfer controls | High — export compliance is an immediate legal risk |
| CCW LAWS discussions (ICRC position) | Medium — IHL constraints shaping future treaty obligations |
| UK MoD AI Strategy obligations | Medium — Defence AI Strategy (2022) implementation requirements |

---

## Quick Wins

- **Programme protection plan AI annex:** `09-risks-by-category.rq` (Security) + `03-controls-by-dimension.rq` (Robustness) → MITRE ATLAS-grounded threat model
- **DoD RAI self-assessment:** `03-controls-by-dimension.rq` (HumanOversight + Accountability) → structured evidence against all five DoD RAI principles
- **Export counsel brief:** `10-obligations-by-stakeholder.rq` → role-based obligation breakdown for technology transfer legal analysis
- **Allied interoperability review:** `04-cross-framework-equivalents.rq` → map partner nation AI governance to DoD/NATO baseline
