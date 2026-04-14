# IQ:NS — Enterprise

Large enterprises deploying AI across multiple business functions, jurisdictions, and vendor relationships face a compliance coordination problem that is fundamentally different from any single-sector exposure. The challenge is not understanding any one framework — it is managing the intersection of dozens simultaneously, across a portfolio of AI systems, with accountability distributed across product, legal, IT risk, and procurement teams. IQ:NS is the shared semantic layer that makes this tractable.

---

## Who This Is For

| Persona | Pain Point |
|---|---|
| Chief AI Officer / AI Governance Lead | Building an enterprise-wide AI governance programme that satisfies regulators across multiple jurisdictions |
| GRC / Internal Audit Director | Assessing AI system portfolio against all applicable frameworks without duplicate effort |
| Chief Procurement Officer | Evaluating AI vendor compliance at scale across a supplier base of hundreds |
| Legal & Regulatory Affairs | Tracking framework changes and their downstream impact on internal AI deployments |
| Board Risk Committee | Demonstrating AI governance maturity to investors, rating agencies, and regulators |

---

## Regulatory Surface

Enterprises face horizontal obligations that cut across all sector-specific rules. The universal baseline:

| Framework | Why It Applies |
|---|---|
| **EU AI Act** | Any enterprise deploying AI affecting EU persons — regardless of headquarters — is in scope |
| **ISO 42001** | De facto certification standard demanded by enterprise clients, insurers, and public procurement |
| **NIST AI RMF** | Reference framework for US-operating enterprises; increasingly cited in contracts and board-level policies |
| **ISO 23894** | Risk management specifically for AI — maps to enterprise ERM programmes |
| **OECD AI** | Baseline referenced by G7/G20 country regulators in enforcement guidance |
| **IEEE 7000** | Ethical impact assessment — required by some large enterprise procurement standards |
| **PAI Guidelines** | Partnership on AI best practices — referenced in responsible AI pledges and ESG disclosures |

Plus any sector-specific overlay (finance → EBA + SR 11-7; health → FDA SaMD; etc.).

---

## High-Value Use Cases

### 1. Enterprise AI System Inventory and Risk Classification
The foundation of any AI governance programme: know what AI systems you operate, classify each by risk level, and map obligations per system.

```sparql
# Framework inventory — which frameworks apply given your operating jurisdictions?
# → ai/sparql/01-framework-inventory.rq

# For each system: is it high-risk under EU AI Act?
# → ai/sparql/02-high-risk-obligations.rq

# Are any systems in prohibited categories?
# → ai/sparql/A-02-ask-prohibited-practices-present.rq

# Construct risk register across the full portfolio
# → ai/sparql/C-03-construct-risk-register.rq
```

**Outcome:** Structured AI system inventory with risk classification, obligation mapping, and framework citations — the foundational deliverable for any AI governance programme.

### 2. Multi-Framework Compliance Programme Design
Rather than running parallel programmes for ISO 42001, NIST AI RMF, and EU AI Act separately, IQ:NS identifies the unified control set that satisfies all simultaneously.

```sparql
# Cross-framework equivalents — one control, multiple frameworks satisfied
# → ai/sparql/04-cross-framework-equivalents.rq

# Gap analysis — what ISO 42001 requires that existing NIST programme doesn't cover
# → ai/sparql/08-gap-analysis-dimensions.rq

# Full alignment graph — construct the unified control architecture
# → ai/sparql/C-02-construct-alignment-graph.rq
```

**Outcome:** Single integrated AI governance control framework that satisfies regulators, auditors, and clients across jurisdictions — eliminates redundant parallel compliance workstreams.

### 3. AI Vendor / Third-Party Due Diligence at Scale
Enterprises procuring AI from hundreds of vendors need a repeatable, structured assessment process that maps to actual regulatory obligations.

```sparql
# Controls by dimension — generate vendor questionnaire from regulatory requirements
# → ai/sparql/03-controls-by-dimension.rq

# Assessment types — what validation must the vendor have done?
# → ai/sparql/12-assessment-types.rq

# Does vendor's ISO 42001 cert satisfy EU AI Act deployer obligations?
# → ai/sparql/04-cross-framework-equivalents.rq
```

**Outcome:** Regulatory-grounded vendor due diligence framework; questionnaire items are traceable to specific articles — defensible in procurement audits and regulatory examinations.

### 4. Board and ESG Reporting
ESG rating agencies (MSCI, Sustainalytics), proxy advisors, and institutional investors increasingly assess AI governance as a material risk factor. Board reports need structured, verifiable data.

```sparql
# Principles catalogue — map ESG AI commitments to regulatory obligations
# → ai/sparql/14-principles-catalogue.rq

# Dimensions covered — demonstrate breadth of governance programme
# → ai/sparql/03-controls-by-dimension.rq

# Compliance profile — system-level attestation
# → ai/sparql/C-01-construct-compliance-profile.rq
```

**Outcome:** Structured AI governance disclosure backed by regulatory citations — suitable for CDP, GRI, or TCFD-style AI governance annexes.

### 5. Regulatory Change Management
When EU AI Act implementing acts, NIST updates, or ISO revisions publish, enterprises need to know which internal systems and controls are affected — immediately.

```sparql
# Related concepts — what changed in the updated framework affects which controls?
# → ai/sparql/11-related-concepts.rq

# Gap analysis re-run against updated framework version
# → ai/sparql/08-gap-analysis-dimensions.rq

# Framework monitoring (IQ:NS currency alerting — Phase 1.4)
# → ai/sparql/01-framework-inventory.rq  (check dct:modified dates)
```

**Outcome:** Early-warning change management; compliance team knows exactly which systems and controls require review before a regulatory deadline.

---

## Key Dimensions for Enterprise AI Governance

`ai:Accountability` · `ai:Transparency` · `ai:Fairness` · `ai:HumanOversight` · `ai:Privacy` · `ai:Security` · `ai:Robustness` · `ai:Sustainability`

---

## Enterprise Integration Patterns

| Integration | How IQ:NS Enables It |
|---|---|
| **ServiceNow / Archer GRC** | Export SPARQL query results as JSON → load into GRC tool as control evidence |
| **Jira / ADO** | Generate obligation-linked tickets for development teams from `05-requirements-by-lifecycle.rq` |
| **PowerBI / Tableau** | `03-controls-by-dimension.rq` results as heatmap data source |
| **LLM Compliance Assistant** | IQ:NS as grounded RAG source — agents call graph, synthesise readable output |
| **Contract Management** | Extract applicable obligations per counterparty jurisdiction → embed in contract schedules |

---

## Quick Wins

- **Board pack (30 min):** `C-03-construct-risk-register.rq` → formatted risk register with citations
- **ISO 42001 gap sprint:** `08-gap-analysis-dimensions.rq` → prioritised remediation backlog in one query
- **Investor due diligence response:** `C-01-construct-compliance-profile.rq` → structured AI governance attestation
- **Audit committee update:** `01-framework-inventory.rq` + `03-controls-by-dimension.rq` → coverage matrix across all frameworks
