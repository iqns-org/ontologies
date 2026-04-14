# IQ:NS — Legal & LegalTech

Legal AI sits in the highest-accountability intersection of any sector: AI systems influencing judicial decisions, legal advice, and access to justice trigger EU AI Act Annex III point 8 (administration of justice and democratic processes) — one of the most restricted categories. Simultaneously, bar associations across every major jurisdiction are issuing AI ethics rules that bind practising lawyers. E-discovery AI, contract review tools, and legal research platforms each face distinct obligation sets. IQ:NS maps them all.

---

## Who This Is For

| Persona | Pain Point |
|---|---|
| General Counsel / Managing Partner | Understanding bar association AI ethics obligations alongside EU AI Act before deploying legal AI tools |
| LegalTech Product Lead | Demonstrating compliance to law firm and in-house clients who are themselves subject to professional regulation |
| Courts / Judicial Technology Officer | Navigating EU AI Act Annex III restrictions on AI in judicial decision-making |
| E-Discovery / Litigation Technology Lead | Meeting evidentiary integrity and explainability requirements for AI-assisted document review |
| Access to Justice / Legal Aid AI | Ensuring AI legal assistance tools meet rights-preservation and non-discrimination obligations |

---

## Regulatory Surface

| Framework | Key Legal Exposure |
|---|---|
| **EU AI Act Annex III pt. 8** | AI intended to assist judicial authorities in fact-finding, law interpretation, or decision-making is high-risk; AI influencing electoral and democratic processes also covered |
| **EU AI Act Art. 5** | AI systems that manipulate persons — relevant for legal advice AI used in adversarial contexts |
| **EU GDPR AI** (`eu-gdpr-ai`) | Legal proceedings involve special category data; Art. 22 automated decision rights directly relevant to AI-assisted legal determinations |
| **IEEE 7000** (`ieee-7000`) | Ethical impact assessment — applicable to AI in high-stakes legal contexts |
| **PAI Guidelines** (`pai-guidelines`) | Responsible AI in high-stakes decisions — referenced in bar association AI guidance |
| **UNESCO AI Ethics** (`unesco-ai`) | Access to justice and rule of law explicitly referenced in the Recommendation |

---

## High-Value Use Cases

### 1. Judicial AI — High-Risk Classification and Restrictions
AI systems assisting judges in research, case management, sentencing analysis, or fact-finding are subject to EU AI Act's strictest high-risk obligations and face additional restrictions under Art. 13 (transparency to courts).

```sparql
# High-risk obligations — full Title III applies
# → ai/sparql/02-high-risk-obligations.rq  (filter: eu-ai-act)

# Prohibited practices — manipulative or subliminal AI in legal contexts
# → ai/sparql/06-prohibited-practices.rq

# Human oversight — mandatory; judge must retain final decision authority
# → ai/sparql/A-03-ask-human-oversight-covered.rq

# Transparency obligations — what must be disclosed to courts and parties?
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Transparency)
```

**Outcome:** Structured obligation register for court technology programmes — defensible in constitutional challenge and regulatory examination.

### 2. Law Firm AI Governance Programme
Law firms deploying AI for legal research, contract review, or client advice face bar association ethics obligations (confidentiality, competence, supervision) layered over EU AI Act deployer obligations.

```sparql
# Stakeholder obligations: law firm as Deployer
# → ai/sparql/10-obligations-by-stakeholder.rq

# Accountability controls — supervision and responsibility chains
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Accountability)

# Assessment types — what validation must the firm conduct?
# → ai/sparql/12-assessment-types.rq

# Gap analysis: existing data protection programme vs. AI-specific obligations
# → ai/sparql/08-gap-analysis-dimensions.rq
```

**Outcome:** AI governance framework that satisfies both the bar and the regulator — structured for senior partner approval and PII committee review.

### 3. LegalTech Vendor Compliance Demonstration
Law firms and in-house teams require LegalTech vendors to demonstrate AI governance before procurement. IQ:NS generates the evidence pack.

```sparql
# Compliance profile — system-level attestation
# → ai/sparql/C-01-construct-compliance-profile.rq

# Controls by dimension — respond to procurement questionnaires
# → ai/sparql/03-controls-by-dimension.rq

# Explainability controls — critical for legal AI
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Explainability)
```

### 4. E-Discovery AI — Evidentiary Integrity and Proportionality
AI-assisted document review and predictive coding must meet evidentiary standards and proportionality requirements. Courts increasingly require documentation of AI methodology.

```sparql
# Transparency and explainability controls
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Transparency, ai:Explainability)

# Reliability controls — accuracy obligations for evidentiary AI
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Reliability)

# Assessment types — validation required before use in proceedings
# → ai/sparql/12-assessment-types.rq
```

### 5. Access to Justice AI — Rights Preservation
AI legal assistance tools (chatbots, self-help platforms) deployed for unrepresented litigants must preserve rights including the right to explanation, to contest decisions, and to human fallback.

```sparql
# Rights inventory — what rights must the AI preserve?
# → ai/sparql/07-rights-inventory.rq

# Fairness controls — non-discrimination in AI legal assistance
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Fairness)

# Human oversight — fallback to human legal adviser
# → ai/sparql/A-03-ask-human-oversight-covered.rq
```

---

## Key Dimensions for Legal AI

`ai:Accountability` · `ai:Transparency` · `ai:Explainability` · `ai:HumanOversight` · `ai:Fairness` · `ai:Reliability` · `ai:Privacy`

---

## Sector-Specific Graph Extensions Needed

| Gap | Priority |
|---|---|
| ABA Model Rules AI amendments (US) | High — competence, supervision, confidentiality for AI-assisted legal work |
| SRA AI guidance (UK Solicitors Regulation Authority) | High — binding on UK solicitors |
| CCBE AI guidelines (EU Bar Associations) | High — European Council of Bars position on AI |
| EU AI Act Art. 13 transparency to courts | Medium — specific court-facing disclosure requirements not fully modelled |
| GDPR special category data in legal proceedings | Medium — Art. 9(2)(f) exception nuances |

---

## Quick Wins

- **Bar ethics compliance checklist:** `03-controls-by-dimension.rq` (Accountability + Transparency) → map to ABA Rules 1.1, 5.3 obligations
- **Court submission AI methodology note:** `12-assessment-types.rq` + `03-controls-by-dimension.rq` (Reliability) → structured methodology documentation
- **Partner committee AI governance memo:** `C-01-construct-compliance-profile.rq` → firm-wide AI governance attestation
- **Vendor RFP response:** `04-cross-framework-equivalents.rq` → show how existing certifications satisfy legal sector obligations
