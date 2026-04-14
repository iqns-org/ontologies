# Vega Chart Templates for IQ:NS

This folder contains placeholder-driven Vega/ Vega-Lite chart templates for the app.
Each template uses Mustache placeholders (`{{ }}`) so backend or runtime interpolation can fill data and settings.

## Usage pattern
1. Load template JSON from file.
2. Replace placeholders with real values before rendering.
3. Pass resulting spec to Vega/Vega-Lite renderer.

Example:

```js
import fs from 'fs'
import Mustache from 'mustache'

const template = fs.readFileSync('v0/vega/chart-risk-level.json', 'utf-8')
const renderData = {
  title: 'AI Risk by Category',
  data: JSON.stringify([...]),
  xField: 'category',
  yField: 'riskScore'
}
const spec = JSON.parse(Mustache.render(template, renderData))
// then render via vegaEmbed or vega-lite API
```

## Covered templates
- Risk distribution
- Compliance score timeline
- Framework coverage chart
- Gap analysis heatmap
- Control status donut
- Incident trend area
- Audit readiness radial gauge
- Crosswalk relationship graph
