# IQ:NS — AI Sector

AI companies and research labs building foundation models, applied AI products, or AI-enabled SaaS face the broadest and most rapidly-evolving compliance surface of any sector. IQ:NS is the fastest path from "what regulations affect us?" to a defensible, auditable answer.

---

## Who This Is For

| Persona | Pain Point |
|---|---|
| CISO / Head of AI Safety | Mapping internal risk controls to regulatory obligations across jurisdictions |
| AI Product / ML Engineer | Understanding which technical requirements (watermarking, logging, human oversight) apply to a specific system |
| Legal / Policy Counsel | Tracking framework changes and implementing acts without manual document review |
| Board / C-Suite | Demonstrating governance posture to investors, customers, and regulators |

---

## Regulatory Surface

AI companies face obligations from **every framework in the graph** but face particular exposure under:

| Framework | Key Exposure |
|---|---|
| **EU AI Act** | High-risk classification, prohibited practices (Art. 5), GPAI model obligations (Art. 51–55), CE marking |
| **NIST AI RMF + AI 100-1** | Adversarial ML threats, bias, robustness — increasingly cited in US procurement and contracts |
| **OWASP LLM Top 10** | Prompt injection, insecure output handling, supply-chain risk — security review baseline |
| **MITRE ATLAS** | Threat taxonomy for adversarial attacks on ML — red-team and incident response |
| **ISO 42001** | AI management system certification — primary enterprise sales enabler |
| **UNESCO AI Ethics** | Soft-law baseline increasingly referenced in government procurement |

---

## High-Value Use Cases

### 1. Pre-Launch Compliance Clearance
Before shipping a new AI feature or model, determine the exact obligation set.

```sparql
# Is the system in a prohibited category?
# → ai/sparql/06-prohibited-practices.rq

# What high-risk obligations apply?
# → ai/sparql/02-high-risk-obligations.rq  (filter: eu-ai-act)

# Is human oversight covered?
# → ai/sparql/A-03-ask-human-oversight-covered.rq
```

**Outcome:** Pass/fail checklist with article citations; ready for legal sign-off in hours, not weeks.

### 2. LLM / GenAI Security Threat Model
Structurally connect OWASP LLM Top 10 + MITRE ATLAS + NIST AI 100-1 into a unified risk register.

```sparql
# All security risks, cross-framework
# → ai/sparql/09-risks-by-category.rq  (filter: ai:Security)

# Control set that addresses them
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Security)
```

**Outcome:** Single risk register replacing three separate document reviews.

### 3. ISO 42001 Certification Readiness
Map existing controls to ISO 42001 Annex A, identify gaps.

```sparql
# Gap analysis vs. any existing programme (e.g., NIST AI RMF)
# → ai/sparql/08-gap-analysis-dimensions.rq

# Cross-framework equivalents — find controls that satisfy multiple frameworks
# → ai/sparql/04-cross-framework-equivalents.rq
```

**Outcome:** Structured gap register; accelerates certification audit by months.

### 4. GPAI Model Provider Obligations (EU AI Act Title VII)
For foundation model providers specifically — Art. 51–55 obligations, systemic risk thresholds, transparency requirements.

```sparql
# All obligations by stakeholder role (Provider / Deployer / Operator)
# → ai/sparql/10-obligations-by-stakeholder.rq
```

### 5. Jurisdiction Expansion
Entering a new market (Singapore, Canada, UK)? Instantly surface the delta obligations.

```sparql
# Inventory all active frameworks
# → ai/sparql/01-framework-inventory.rq

# Find conceptual equivalents across jurisdictions
# → ai/sparql/04-cross-framework-equivalents.rq
```

---

## Key Dimensions for AI Companies

`ai:Safety` · `ai:Security` · `ai:Transparency` · `ai:HumanOversight` · `ai:Robustness` · `ai:Explainability` · `ai:Accountability`

---

## Quick Wins

- **Due diligence pack for investors:** run `C-01-construct-compliance-profile.rq` against your system descriptor → board-ready RDF compliance profile
- **Customer trust questionnaire answers:** query specific controls by dimension in seconds
- **Regulatory monitoring:** IQ:NS framework currency alerting fires when source frameworks update — no manual tracking

---

## Roadmap Relevance

- **MCP Server (P3.3):** AI companies are primary adopters — agents call `ai/get_obligations()` directly
- **`self/`:** IQ:NS itself is an AI system; this sector's use cases are the product's own dogfood
