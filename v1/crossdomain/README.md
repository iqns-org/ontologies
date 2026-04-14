# Cross-Domain Alignments

This directory contains SKOS alignment files that map semantically equivalent concepts **across different domains** (AI ↔ Legal, AI ↔ Finance, AI ↔ Health, etc.).

## Purpose

While each domain (`v0/ai/`, `v0/finance/`, `v0/health/`, etc.) has internal coherence, many obligations and controls span multiple domains:

- **Automated decision-making** is regulated by both EU AI Act (Title III) and GDPR (Article 22)
- **Model risk** appears in both AI frameworks (NIST AI RMF) and financial regulations (SR 11-7, Basel III)
- **Medical device AI** is subject to both EU AI Act (Annex III.5) and EU MDR/IVDR

Cross-domain alignments make these relationships explicit and queryable.

## Structure

Each file maps concepts between two domains using SKOS alignment relations:

```
ai-legal-skos.ttl       ← EU AI Act ↔ GDPR alignments
ai-finance-skos.ttl     ← EU AI Act ↔ Sr 11-7, Basel III, DORA
ai-health-skos.ttl      ← EU AI Act ↔ FDA SaMD, HIPAA, EU MDR
```

## Alignment Relations

| Relation | Use When | Example |
|---|---|---|
| `skos:exactMatch` | 1-to-1 semantic equivalence | `euai:AutomatedDecision skos:exactMatch gdpr:AutomatedDecisionMaking` |
| `skos:broadMatch` | Framework A is broader | `euai:ProvidedObligation skos:broadMatch gdpr:ControllerResponsibility` |
| `skos:narrowMatch` | Framework A is narrower | `gdpr:AutomatedDecision skos:narrowMatch euai:AutomatedEmploymentDecision` |
| `skos:relatedMatch` | Associated but not hierarchical | `euai:DataGovernance skos:relatedMatch gdpr:LawfulBasis` |
| `skos:closeMatch` | Similar but possibly non-equivalent | Use sparingly |

## Querying Cross-Domain Alignments

**Find all GDPR obligations related to a given EU AI Act concept:**

```sparql
PREFIX euai: <https://iqns.org/v0/eu-ai-act#>
PREFIX gdpr: <https://iqns.org/v0/eu-gdpr-ai#>
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>

SELECT ?gdrpConcept ?relation WHERE {
  euai:HighRiskPersonalDataProcessing ?relation ?gdprConcept .
  FILTER (?relation IN (skos:exactMatch, skos:broadMatch, skos:relatedMatch))
}
```

**Find all high-risk AI contexts that also implicate privacy law:**

```sparql
PREFIX euai:   <https://iqns.org/v0/eu-ai-act#>
PREFIX gdpr:   <https://iqns.org/v0/eu-gdpr-ai#>
PREFIX skos:   <http://www.w3.org/2004/02/skos/core#>

SELECT ?aiConcept ?gdprConcept (SAMPLE(?def) AS ?definition) WHERE {
  ?aiConcept a euai:HighRiskCategory ;
             skos:relatedMatch ?gdprConcept .
  ?gdprConcept a gdpr:LegalObligation ;
               skos:definition ?def .
}
GROUP BY ?aiConcept ?gdprConcept
```

## Adding New Cross-Domain Alignments

1. **Identify the two domains** you're aligning (e.g., `ai` and `finance`)
2. **Create or update** `{domain1}-{domain2}-skos.ttl`
3. **Group alignments by theme** using `skos:Collection`
4. **Document rationale** in comments explaining why alignments exist
5. **Use appropriate `skos:*Match`** relation (exactMatch / broadMatch / relatedMatch)
6. **Submit PR** for review by domain experts

## Current Coverage

- ✅ `ai-legal-skos.ttl` — EU AI Act ↔ GDPR (foundational alignment)
- ⏳ `ai-finance-skos.ttl` — In progress
- ⏳ `ai-health-skos.ttl` — In progress
- ⏳ `finance-enterprise-skos.ttl` — Not started

See [`todo/PLAN.md`](../todo/PLAN.md) for roadmap.

