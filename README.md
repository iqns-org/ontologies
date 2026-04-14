# IQ:NS

IQ:NS is a **operating system for agentic organisations**. 

Each domain (AI, Finance, Health, Legal, …) has a semantic graph that canonicalises the real-world frameworks, regulations, and standards governing that domain into a single queryable, machine-readable layer.

The four pillars are the product in one sentence:

| Pillar | What it means |
|---|---|
| **Connect** | RDF/OWL/SKOS graphs that link every framework, concept, and obligation to a canonical vocabulary — across domains and across jurisdictions |
| **Automate** | CONSTRUCT inferencing, agentic control, REST API, SPARQL endpoint, MCP server |
| **Focus** | Given your context (who you are, where you operate, what you build), surface exactly the obligations, controls, and gaps that apply — nothing else |
| **Engage** | The surfaces through which stakeholders act on the intelligence - Web UI, co-pilot, charts, graphs, audit-grade exports, board packs, workbench tools |

---

## Sample Repository Layout

```
v1/
├── ai/                 ← AI governance (v1)
├── finance/            ← FinanceGraph (v1)
├── health/             ← HealthGraph (v1)
├── employment/         ← EmploymentGraph (v1)
├── legal/              ← LegalGraph (v1)
├── government/         ← GovtGraph (v1)
├── insurance/          ← InsuranceGraph (v1)
├── enterprise/         ← EnterpriseGraph (v1)
└── startup/            ← StartupGraph (v1)
```

---