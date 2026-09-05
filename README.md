<p align="center">
  <img src="./assets/profile-console-v4.svg" width="100%" alt="Vijwal Mahendrakar — AI Engineer focused on reliable production AI" />
</p>

<p align="center">
  <a href="#identity"><code>identity</code></a> &nbsp;·&nbsp;
  <a href="#experience"><code>experience.log</code></a> &nbsp;·&nbsp;
  <a href="#systems"><code>systems/</code></a> &nbsp;·&nbsp;
  <a href="#education"><code>education</code></a> &nbsp;·&nbsp;
  <a href="#toolchain"><code>toolchain.lock</code></a>
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/vijwal-mahendrakar-1b6a8215a/"><img src="https://img.shields.io/badge/linkedin-connect-20262d?style=flat-square&logo=linkedin&logoColor=8baaa7" alt="LinkedIn" /></a>
  <a href="mailto:vijwalmahendrakar@gmail.com"><img src="https://img.shields.io/badge/email-personal-20262d?style=flat-square&logo=gmail&logoColor=8baaa7" alt="Personal email" /></a>
  <a href="mailto:mahendrakar.v@northeastern.edu"><img src="https://img.shields.io/badge/email-northeastern-20262d?style=flat-square&logo=microsoftoutlook&logoColor=918ca3" alt="Northeastern email" /></a>
</p>

<a id="identity"></a>

## `01 / identity`

<table>
<tr>
<td width="61%" valign="top">

```toml
[engineer]
name = "Vijwal Mahendrakar"
role = "AI Engineer"
base = "Boston, MA"

[work]
focus = ["Generative AI", "Agents", "RAG"]
principle = "reliability over impressive demos"
builds = "systems that retrieve, reason, and verify"

[availability]
target = "Spring 2027 co-op"
start = "January 2027"
also_open_to = ["AI/ML internships", "full-time AI roles"]
```

</td>
<td width="39%" valign="top">

### `current_signal`

**M.S. Artificial Intelligence**  
Northeastern University

I work at the layer between an LLM demo and a dependable AI product: retrieval, orchestration, evaluation, guardrails, latency, and deployment.

> I care about what happens after the model answers.

</td>
</tr>
</table>

<a id="experience"></a>

## `02 / experience.log`

<table>
<tr>
<td width="58%" valign="top">

### Kideon
`AI Engineer Intern` · `Remote` · `U.S.-based`  
**Dec 2024 → Aug 2025**

Built the intelligence layer for a pre-launch gym and healthcare platform: health-record RAG, persistent patient memory, personalized plan generation, and a verification path for unsafe or weakly grounded output.

<details>
<summary><code>inspect role</code></summary>
<br>

- Triaged uploaded records for relevance, quality, and malformed data before ingestion.
- Grounded workout and nutrition plans in longitudinal patient history with source-level traceability.
- Used an LLM-as-judge pass to score consistency and route low-confidence results to human review.
- Built FastAPI and Docker microservices with Redis-backed retrieval caching; the team later deployed the system on AWS.

`RAG` `FastAPI` `Docker` `Redis` `AWS` `LLM evaluation`

</details>

</td>
<td width="42%" valign="top">

### Jio Platforms
`Video Analytics Intern` · `Hybrid` · `Hyderabad`  
**Nov 2023 → May 2024**

| signal | result |
|:--|--:|
| detection + OCR | **92%+** |
| inference latency | **−35%** |
| curated samples | **20,000+** |

<details>
<summary><code>inspect role</code></summary>
<br>

- Built real-time vehicle and license-plate recognition with YOLOv7 and PaddleOCR.
- Optimized inference with ONNX Runtime for live CCTV and smart-camera prototypes.
- Created scraping and annotation tooling for motion blur, occlusion, and other edge cases.
- Fine-tuned Stable Diffusion to generate training data for a future baby-monitor product spanning smile, cry, and movement detection.

</details>

</td>
</tr>
</table>

<a id="systems"></a>

## `03 / systems/`

### `featured.01` Pharmaceutical Safety RAG

<table>
<tr>
<td width="66%" valign="top">

**A production-oriented agentic RAG system over ~15,000 FDA drug labels.**

Current-label PDFs preserve real tables and document layout; historical DailyMed SPL XML preserves versioned safety changes. The system combines deterministic ingestion, hybrid retrieval, reranking, controlled agent flow, guardrails, caching, observability, and evaluation-gated releases.

<details>
<summary><code>open architecture notes</code></summary>
<br>

- Docling for layout-aware PDF parsing, with pdfplumber as the table fallback.
- lxml/XPath against SPL LOINC section codes for historical XML extraction.
- Qdrant dense retrieval + BM25, fused with RRF and followed by cross-encoder reranking.
- LangGraph routing and verification with PostgreSQL, Redis, FastAPI, and Docker.

</details>

<!-- TODO: Add repository URL and final evaluation metrics. -->

</td>
<td width="34%" valign="top">

```yaml
corpus:
  current: PDF
  history: SPL_XML
retrieval:
  - dense
  - BM25
  - reranker
control:
  - routing
  - guardrails
  - evaluation
status: implemented
```

</td>
</tr>
</table>

---

### `featured.02` Agentic Game Recommendation System

<table>
<tr>
<td width="35%" valign="top">

```yaml
query: player_intent
retrieve:
  - ChromaDB
  - BM25
  - selective_HyDE
rank:
  - bi_encoder
  - QLoRA_reranker
personalize: Steam
status: implemented
```

</td>
<td width="65%" valign="top">

**A recommendation engine that treats discovery as a reasoning problem—not a genre filter.**

Combines hybrid retrieval, reciprocal-rank fusion, LLM-assisted tag enrichment, self-distilled training pairs, hard negatives, personalized Steam-library context, and explanation generation.

<details>
<summary><code>open architecture notes</code></summary>
<br>

- Fine-tuned a bi-encoder and QLoRA reranker from self-distilled relevance pairs.
- Used LangGraph to coordinate parsing, retrieval, reranking, personalization, and explanation.
- Added two-level Redis caching, ONNX-optimized inference, FastAPI services, Docker, and Ollama.

</details>

<!-- TODO: Add repository URL and final ranking/latency metrics. -->

</td>
</tr>
</table>

### `selected builds`

<table>
<tr>
<td width="50%" valign="top">

#### [VOID AI ↗](https://github.com/aatmaj28/Void-AI)

**Analyst-coverage gap intelligence** across **1,700+ U.S. equities**, combining SEC-filings RAG with a five-agent CrewAI debate workflow.

Owned the backtester, compare workflow, portfolio UI, authentication integration, history APIs, migrations, and real-market-data fixes.

`Next.js` `FastAPI` `CrewAI` `Supabase` `pgvector`

</td>
<td width="50%" valign="top">

#### [Equity Performance Screener ↗](https://github.com/Vijwalmahen/equity-screener)

**Time-aware ML for next-quarter S&amp;P 500 outperformance**, with financial baselines, leakage tests, explainability, uncertainty, and transaction costs.

`held-out AUC 0.577` · `16-quarter walk-forward AUC 0.566`

`XGBoost` `SHAP` `FastAPI` `React`

</td>
</tr>
</table>

<details>
<summary><b><code>side_quest</code> <a href="https://github.com/Chandi713/Hackathon---End-Of-The-World">ResilienceAI</a></b> · 8-agent supply-chain risk simulation</summary>
<br>

Contributed country selection and full-stack API integration to a LangGraph platform exploring cascading risk across **266 countries** and **25 years** of multi-domain data.

`LangGraph` `Python` `FastAPI` `Next.js` `TypeScript` `Recharts`

</details>

<a id="education"></a>

## `04 / education`

<table>
<tr>
<td width="52%" valign="top">

### Northeastern University

**M.S. Artificial Intelligence**  
Boston, MA · Sep 2025 → Expected 2027

`GPA 3.84 / 4.00`

</td>
<td width="48%" valign="top">

### Vellore Institute of Technology

**B.Tech CSE · Internet of Things**  
Vellore, India · 2021 → 2025

`CGPA 8.78 / 10`  
Major project: LLM quantization and model-size reduction

</td>
</tr>
</table>

<a id="toolchain"></a>

## `05 / toolchain.lock`

<table>
<tr>
<td width="33%" valign="top">

**AI systems**

`LangGraph` `LangChain`  
`Hugging Face` `RAG`  
`LLM evaluation`  
`agentic workflows`

</td>
<td width="34%" valign="top">

**Models + retrieval**

`PyTorch` `TensorFlow`  
`scikit-learn` `XGBoost`  
`Qdrant` `pgvector`  
`PostgreSQL` `Redis`

</td>
<td width="33%" valign="top">

**Production**

`FastAPI` `REST APIs`  
`Docker` `AWS` `Linux`  
`ONNX Runtime` `OpenCV`  
`Git` `SQL`

</td>
</tr>
</table>

<details>
<summary><code>show full inventory</code></summary>
<br>

**Languages:** Python, C++, SQL, JavaScript, Java, HTML/CSS  
**ML/CV:** PyTorch, TensorFlow, Keras, scikit-learn, XGBoost, Pandas, NumPy, OpenCV, YOLO, PaddleOCR  
**AI:** LLMs, Generative AI, RAG, NLP, reinforcement learning, LangChain, LangGraph, Hugging Face  
**Platforms:** PostgreSQL, Supabase, pgvector, Qdrant, Redis, FastAPI, Docker, AWS, ONNX Runtime, Linux

</details>

### `currently_compiling`

```text
multi-agent reliability      routing · memory · guardrails · human review
RAG evaluation               retrieval · grounding · latency · cost
efficient LLM deployment     quantization · pruning · optimized inference
```

---

<p align="center">
  <a href="https://github.com/Vijwalmahen?tab=repositories"><img src="https://img.shields.io/badge/browse-repositories-20262d?style=flat-square&logo=github&logoColor=8baaa7" alt="Browse repositories" /></a>
  <a href="https://www.linkedin.com/in/vijwal-mahendrakar-1b6a8215a/"><img src="https://img.shields.io/badge/start-a_conversation-20262d?style=flat-square&logo=linkedin&logoColor=918ca3" alt="Start a conversation on LinkedIn" /></a>
</p>

<p align="center"><sub><code>status: building systems that earn trust</code></sub></p>
