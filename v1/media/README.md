# IQ:NS — Media & Content

Generative AI has made media the first sector to experience direct regulatory enforcement of AI-specific content obligations. EU AI Act Art. 50 (transparency for synthetic content) is already in force. The AI-generated content labelling requirements, deepfake rules, and platform liability framework are live obligations — not future risk. Simultaneously, content recommendation AI on platforms, editorial AI, and AI in advertising each generate distinct obligation sets under existing media law. IQ:NS maps them all.

---

## Who This Is For

| Persona | Pain Point |
|---|---|
| Chief Content / Editorial Officer | Ensuring AI-generated or AI-assisted content meets disclosure and labelling obligations |
| Platform Trust & Safety / Policy Lead | Navigating EU AI Act Art. 50, DSA, and national deepfake legislation simultaneously |
| Advertising Technology Lead | Mapping AI-targeted advertising obligations under GDPR, DSA, and emerging AI Act guidance |
| Broadcast / Streaming General Counsel | Advising on synthetic voice, synthetic presenter, and AI-scripted content obligations |
| GenAI Content Tool Vendor | Demonstrating compliance to media clients operating under Art. 50 obligations |

---

## Regulatory Surface

| Framework | Key Media Exposure |
|---|---|
| **EU AI Act Art. 50** | Transparency obligations for AI-generated content already in force: synthetic audio/video/image must be labelled; deepfakes interacting with real persons require disclosure; AI-generated text on public interest matters must be marked |
| **EU AI Act Art. 5(1)(b)** | AI that subliminally manipulates persons — directly relevant to AI-optimised engagement and recommendation systems |
| **NIST AI 100-1** (`nist-ai-100-1`) | Synthetic content and deepfake security risks — technical baseline for content authentication |
| **MITRE ATLAS** (`mitre-atlas`) | Adversarial content generation attack taxonomy — threat model for CSAM, disinformation, influence operations |
| **UNESCO AI Ethics** (`unesco-ai`) | Media pluralism, freedom of expression, and AI obligations — soft law referenced by public broadcasters |
| **Google SAIF** (`google-saif`) | Secure AI Framework — supply-chain and content integrity controls for media AI pipelines |
| **PAI Guidelines** (`pai-guidelines`) | Synthetic media responsible practices — adopted by major studios and platforms |

---

## High-Value Use Cases

### 1. Art. 50 Synthetic Content Labelling — Compliance Audit
EU AI Act Art. 50 is in force now. Any system generating synthetic audio, video, images, or public-interest text must implement machine-readable labelling (C2PA, watermarking) and user-facing disclosure. Non-compliance is enforceable by national market surveillance authorities.

```sparql
# Transparency obligations — Art. 50 disclosure requirements
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Transparency)

# All high-risk obligations that may additionally apply (if system is Annex III)
# → ai/sparql/02-high-risk-obligations.rq

# Prohibited practices — subliminal manipulation, deepfakes of real persons without consent
# → ai/sparql/06-prohibited-practices.rq

# Stakeholder obligations: who labelling obligation falls on (Provider vs. Deployer)
# → ai/sparql/10-obligations-by-stakeholder.rq
```

**Outcome:** Structured Art. 50 compliance checklist with article citations — the minimum viable obligation set for any generative AI content product operating in the EU.

### 2. Deepfake and Synthetic Media Risk Assessment
Non-consensual deepfakes of real persons, political disinformation fabrications, and synthetic audio scams are either prohibited under Art. 5 or trigger mandatory disclosure under Art. 50. The boundary requires careful legal mapping.

```sparql
# Prohibited practices — categorical prohibition check
# → ai/sparql/A-02-ask-prohibited-practices-present.rq

# Security risks — synthetic media attack vectors (MITRE ATLAS)
# → ai/sparql/09-risks-by-category.rq  (filter: ai:Security)

# Transparency and safety controls
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Transparency, ai:Safety)
```

**Outcome:** Legal boundary memo distinguishing prohibited content from disclosure-required content — essential before shipping any generative video or audio product.

### 3. Content Recommendation AI — Manipulation Prohibition
Algorithmic recommendation systems optimised for engagement may trigger EU AI Act Art. 5(1)(b) (subliminal manipulation exploiting vulnerabilities). The DSA additionally requires transparency and audit obligations for very large platforms.

```sparql
# Prohibited practices — subliminal manipulation assessment
# → ai/sparql/06-prohibited-practices.rq

# Transparency controls — recommendation system disclosure obligations
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Transparency)

# Human oversight — editorial override and content moderation requirements
# → ai/sparql/A-03-ask-human-oversight-covered.rq
```

### 4. AI in Advertising — Targeting and Profiling Obligations
AI-targeted advertising intersects GDPR, DSA (prohibition on targeting minors), and EU AI Act transparency obligations. Profiling-based ad targeting now carries specific consent and transparency requirements.

```sparql
# Privacy controls — GDPR profiling and consent requirements
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Privacy)

# Rights inventory — right to object to profiling (Art. 21 GDPR)
# → ai/sparql/07-rights-inventory.rq

# Fairness controls — non-discrimination in AI ad targeting
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Fairness)
```

### 5. GenAI Tool Vendor Compliance for Media Clients
Media companies procuring GenAI tools (scriptwriting, image generation, voice cloning) are the Deployer under EU AI Act — they are responsible for labelling and disclosure obligations triggered by the tool's output.

```sparql
# Compliance profile — attestation for media client procurement
# → ai/sparql/C-01-construct-compliance-profile.rq

# Controls demonstrating Art. 50 capability (watermarking, labelling)
# → ai/sparql/03-controls-by-dimension.rq  (filter: ai:Transparency)

# Assessment types completed
# → ai/sparql/12-assessment-types.rq
```

---

## Key Dimensions for Media AI

`ai:Transparency` · `ai:Safety` · `ai:Accountability` · `ai:Fairness` · `ai:Privacy` · `ai:Security`

---

## Sector-Specific Graph Extensions Needed

| Gap | Priority |
|---|---|
| EU AI Act Art. 50 as structured ai:Obligations (labelling, watermarking, disclosure) | High — currently under-modelled; Art. 50 is in force |
| C2PA (Content Credentials) standard as ai:Control | High — the technical implementation of Art. 50 |
| UK Online Safety Act AI content provisions | High — Ofcom now has powers over AI-generated harmful content |
| US AI-Generated Content Disclosure Acts (state level) | Medium — California, Texas leading; patchwork approach |
| Advertising Standards AI guidance (ASA/UK, FTC/US) | Medium — AI-generated ads obligations |
| EBU (European Broadcasting Union) AI editorial standards | Low — soft guidance; useful for public broadcasters |

---

## Quick Wins

- **Art. 50 compliance sprint:** `03-controls-by-dimension.rq` (Transparency) → 30-minute checklist for every AI content output pipeline
- **Legal hold memo:** `06-prohibited-practices.rq` → define the precise line between permitted and prohibited synthetic content
- **Advertiser trust pack:** `C-01-construct-compliance-profile.rq` → AI transparency attestation for brand safety requirements
- **Newsroom AI policy:** `14-principles-catalogue.rq` → editorial AI principles grounded in UNESCO and PAI guidance
