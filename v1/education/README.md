# IQ:NS — Education

AI in education — adaptive learning platforms, admissions algorithms, student performance prediction, and examination integrity tools — is explicitly high-risk under EU AI Act Annex III point 3. It also intersects the broadest set of data protection obligations of any sector: children's data, special educational needs data, and behavioural data at scale. Simultaneously, EdTech procurement by schools and universities is increasingly governed by national and state regulations that predate the EU AI Act. IQ:NS connects the full obligation stack.

---

## Who This Is For

| Persona | Pain Point |
|---|---|
| Chief Digital / Technology Officer (School / University) | Procuring AI tools without inadvertently deploying high-risk systems without the required governance |
| EdTech Vendor (Product / Compliance Lead) | Winning tenders from public education authorities that now require AI compliance statements |
| Data Protection Officer | Managing children's data obligations alongside EU AI Act requirements |
| Admissions / Assessment Technology Lead | Ensuring AI-assisted admissions and grading systems meet fairness and transparency obligations |
| Education Policy / Regulatory Affairs | Advising institutions on the intersection of EU AI Act, GDPR, and national education law |

---

## Regulatory Surface

| Framework | Key Education Exposure |
|---|---|
| **EU AI Act Annex III pt. 3** | AI used to determine educational access, assess students, monitor examination integrity, and determine learning paths explicitly listed as high-risk |
| **EU GDPR AI** (`eu-gdpr-ai`) | Children's data (under 16) requires parental consent (Art. 8); special category data (disabilities, SEN) under Art. 9; automated decisions about students under Art. 22 |
| **ISO 24027** (`iso-24027`) | Bias in AI — critical for admissions and assessment AI to avoid proxy discrimination |
| **UNESCO AI Ethics** (`unesco-ai`) | Explicit guidance on AI in education and protecting learners |
| **NIST AI RMF** | Fairness and robustness controls — referenced in US Department of Education AI guidance |
| **PAI Guidelines** | Responsible AI in education — referenced by EdTech organisations and UNESCO |
| **IEEE 7000** | Ethical impact assessment — required by some university procurement standards |

---

## High-Value Use Cases

### 1. Admissions AI — High-Risk Obligation Register
Any AI system that influences access to educational institutions (shortlisting, ranking, scoring applications) is high-risk under EU AI Act Annex III. Full Title III obligations apply.

```sparql
# All high-risk obligations
# → ai/sparql/02-high-risk-obligations.rq  (filter: eu-ai-act)

# Prohibited practices — check for prohibited subliminal manipulation or profiling
# → ai/sparql/06-prohibited-practices.rq

# Human oversight — mandatory; final decision must be human-reviewable
# → ai/sparql/A-03-ask-human-oversight-covered.rq

# GDPR rights — applicant right to explanation
# → ai/sparql/07-rights-inventory.rq
```

**Outcome:** Obligation register for admissions AI governance — required before deployment and for annual audit cycle.

### 2. Student Assessment and Grading AI Fairness
AI systems that evaluate student work, predict grades, or determine educational pathways must be assessed for bias across protected characteristics. The 2020 A-level algorithm scandal is the defining cautionary case.

```sparql
# Fairness controls
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Fairness)

# Bias assessment requirements (ISO 24027)
# → ai/sparql/12-assessment-types.rq

# Risks in the fairness dimension
# → ai/sparql/09-risks-by-category.rq  (filter: ai:Fairness)
```

**Outcome:** Structured fairness audit programme with ISO 24027 and EU AI Act citations — table-ready for examination board governance committees.

### 3. Children's Data — Elevated Obligations
Educational AI processes vast quantities of children's data. GDPR Art. 8 (parental consent), UK Children's Code (Age Appropriate Design Code), and US COPPA / FERPA create a layered obligation set beyond standard data protection.

```sparql
# Privacy controls — full cross-framework set
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Privacy)

# Rights inventory — children's specific rights to explanation and contest
# → ai/sparql/07-rights-inventory.rq

# Special category data processing requirements
# → ai/sparql/02-high-risk-obligations.rq
```

### 4. EdTech Vendor Procurement Assessment
Schools and universities are the Deployer under EU AI Act — they inherit obligations when they procure AI tools. Procurement due diligence must now include AI governance assessment.

```sparql
# Controls by dimension — vendor questionnaire grounded in regulation
# → ai/sparql/03-controls-by-dimension.rq

# Does vendor's ISO 42001 satisfy EU AI Act deployer obligations?
# → ai/sparql/04-cross-framework-equivalents.rq

# Gap analysis — what remains uncovered
# → ai/sparql/08-gap-analysis-dimensions.rq
```

### 5. Examination Integrity AI (Proctoring)
Remote proctoring AI using behavioural analysis, facial recognition, or gaze tracking is among the most restricted categories — touching both high-risk AI obligations and potentially prohibited practices (Art. 5 biometric categorisation).

```sparql
# Prohibited practices — biometric data use
# → ai/sparql/06-prohibited-practices.rq

# High-risk obligations if not prohibited
# → ai/sparql/02-high-risk-obligations.rq

# Transparency to students — mandatory disclosure of AI monitoring
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Transparency)
```

---

## Key Dimensions for Education AI

`ai:Fairness` · `ai:Transparency` · `ai:HumanOversight` · `ai:Privacy` · `ai:Accountability` · `ai:Explainability`

---

## Sector-Specific Graph Extensions Needed

| Gap | Priority |
|---|---|
| UK ICO Children's Code (Age Appropriate Design) | High — binding on EdTech serving UK users |
| US FERPA / COPPA intersection with AI | High — US public education sector procurement requirement |
| UNESCO AI in Education Recommendation (operational guidance) | Medium — soft law but referenced in procurement |
| Department for Education (UK) AI in Schools framework | Medium — published 2024; adoption accelerating |
| EU AI Act Art. 26 deployer obligations for education institutions | Medium — not fully modelled as institution-specific guidance |

---

## Quick Wins

- **Governing body AI policy:** `14-principles-catalogue.rq` → foundation for institutional AI ethics statement
- **DPO impact assessment:** `03-controls-by-dimension.rq` (Privacy) + `07-rights-inventory.rq` → DPIA AI annex in 30 minutes
- **Ofsted / accreditation readiness:** `C-01-construct-compliance-profile.rq` → structured posture for inspection
- **Student union / works council briefing:** `07-rights-inventory.rq` → clear statement of student rights under AI systems
