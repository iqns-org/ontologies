# Vega Chart Templates for IQ:NS

This folder contains placeholder-driven Vega/Vega-Lite chart templates for the app. Each template uses Mustache placeholders (`{{ }}`) so backend or runtime interpolation can fill data and options.

## Usage pattern
1. Load template JSON.
2. Render via Mustache with actual values.
3. Parse JSON and feed into Vega/Vega-Lite renderer.

## Chart template <-> SPARQL mapping
- `chart-risk-distribution.json` ↔ `chart-risk-distribution.rq`
- `chart-compliance-timeline.json` ↔ `chart-compliance-timeline.rq`
- `chart-framework-coverage.json` ↔ `chart-framework-coverage.rq`
- `chart-gap-analysis-heatmap.json` ↔ `chart-gap-analysis-heatmap.rq`
- `chart-control-status-donut.json` ↔ `chart-control-status-donut.rq`
- `chart-incident-trend-area.json` ↔ `chart-incident-trend-area.rq`
- `chart-readiness-gauge.json` ↔ `chart-readiness-gauge.rq`
- `chart-crosswalk-graph.json` ↔ `chart-crosswalk-graph.rq`

## Example data payloads (replace in `{{data}}` / `{{nodes}}` / `{{links}}`)

### Risk distribution
```json
[{"category":"Data Privacy","count":15},{"category":"Model Bias","count":23},{"category":"Security","count":11}]
```

### Compliance timeline
```json
[{"date":"2025-01-01","framework":"NIST AI RMF","score":62},{"date":"2025-04-01","framework":"NIST AI RMF","score":69}]
```

### Framework coverage heatmap
```json
[{"framework":"ISO 42001","dimension":"Security","coverage":90},{"framework":"NIST AI RMF","dimension":"Risk","coverage":78}]
```

### Gap analysis heatmap
```json
[{"framework1":"ISO 42001","framework2":"NIST AI RMF","gapStatus":"covered"},{"framework1":"SOC 2","framework2":"ISO 27001","gapStatus":"gap"}]
```

### Control status donut
```json
[{"status":"implemented","count":75},{"status":"in-progress","count":18},{"status":"not-started","count":7}]
```

### Incident trend area
```json
[{"date":"2025-01-01","incidentType":"Data Breach","count":2},{"date":"2025-02-01","incidentType":"Model Drift","count":5}]
```

### Readiness gauge
```json
[{"level":"ready","value":0.65},{"level":"in-progress","value":0.25},{"level":"not-ready","value":0.10}]
```

### Crosswalk graph
`nodes`:
```json
[{"id":"iso42001","name":"ISO 42001","group":"ai"},{"id":"cobit","name":"COBIT","group":"governance"}]
```
`links`:
```json
[{"source":"iso42001","target":"cobit"},{"source":"iso42001","target":"nist-ai-rmf"}]
```
