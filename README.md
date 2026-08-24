<p align="center">
  <img src="./assets/profile-hero.svg" width="100%" alt="Meet Sutariya — Backend Engineering, Data Systems, and Applied AI" />
</p>

<p align="center">
  <a href="https://github.com/meetsutariya4448"><strong>GitHub</strong></a>
  &nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="https://www.linkedin.com/in/meetssutariya"><strong>LinkedIn</strong></a>
  &nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="mailto:meetsutariya5930@gmail.com"><strong>Email</strong></a>
  &nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="https://fitforge-six.vercel.app"><strong>Live build</strong></a>
</p>

---

## 01 / ENGINEERING PROFILE

I am a Computer Science + Data Science undergraduate at Arizona State University, graduating in 2027. My repositories center on backend services, data movement, retrieval systems, and the engineering work required to turn model output into a usable product.

I tend to work across the full path: ingest and normalize data, design the database and API boundary, add retrieval or ML where it earns its place, then test and measure the behavior. I am looking for 2027 software, backend, AI/ML, and data engineering internships where that systems-and-product range is useful.

<table>
  <tr>
    <th align="left">WHAT I BUILD</th>
    <th align="left">HOW I ENGINEER</th>
    <th align="left">WHAT I AM LOOKING FOR</th>
  </tr>
  <tr>
    <td>API-backed products, ingestion pipelines, retrieval systems, protocol gateways</td>
    <td>Relational models, scheduled jobs, tests and CI, evals, benchmarks, containers</td>
    <td>2027 SWE, backend, applied AI/ML, or data engineering internships</td>
  </tr>
</table>

---

## 02 / SELECTED SYSTEMS

### 01 · [TalentScope](https://github.com/meetsutariya4448/talentscope)

#### Job-market intelligence from scheduled ingestion to hybrid retrieval.

Celery workers ingest postings from Greenhouse, Lever, and Adzuna, normalize and deduplicate them, and persist searchable records in PostgreSQL. A FastAPI layer combines GIN full-text search with pgvector HNSW retrieval through Reciprocal Rank Fusion; Redis-backed RAG Q&A and scheduled KMeans role clustering sit on the same data path.

`Python · FastAPI · PostgreSQL · pgvector · Celery · Redis · scikit-learn · Docker`

**Engineering signal:** 1,530-posting measured corpus · hybrid search p95 **39.2 ms** across 600 local samples · **54 tests passing** in GitHub Actions.  
[Repository →](https://github.com/meetsutariya4448/talentscope) · [CI →](https://github.com/meetsutariya4448/talentscope/actions/runs/30116435731) · [Benchmark →](https://github.com/meetsutariya4448/talentscope/blob/main/evals/benchmark.json)

<br>

### 02 · [Portcullis](https://github.com/meetsutariya4448/portcullis)

#### A stateless protocol gateway with a separately evaluated security control plane.

The Go data plane validates MCP headers against JSON-RPC bodies, routes namespaced tools, and bridges legacy upstreams through bounded session pools and a sliding-window circuit breaker. The Python control plane evaluates a three-stage tool-poisoning detector—rules, local embedding similarity, then an LLM classifier with literal evidence-span validation.

`Go · Python · net/http · Prometheus · sentence-transformers · pgvector · Docker`

**Engineering signal:** sourced 139-row scanner corpus · cascade F1 **0.973** under leave-one-out evaluation, with the stricter family-holdout limitation reported alongside it · measured native gateway p50 overhead **+1.30 ms** on the documented local benchmark. The scanner is not yet wired into live gateway enforcement.  
[Repository →](https://github.com/meetsutariya4448/portcullis) · [Architecture →](https://github.com/meetsutariya4448/portcullis/blob/main/ARCHITECTURE.md) · [Evaluation →](https://github.com/meetsutariya4448/portcullis/blob/main/control/evals/REPORT.md)

<br>

### 03 · [FitForge](https://github.com/meetsutariya4448/fitforge)

#### A deployed fitness product with an evaluated retrieval path.

FitForge pairs a React client with a FastAPI/PostgreSQL backend for JWT-authenticated plan generation, workout-session logging, personal-record updates, and progress visualization. Its planning path retrieves fitness guidance with sparse + dense search and cross-encoder reranking before grounded generation through Groq.

`Python · FastAPI · PostgreSQL · React · Recharts · sentence-transformers · Groq · Docker`

**Engineering signal:** working public deployment · Alembic-managed relational model · 30-query retrieval ablation where hybrid search reached **R@5 0.900**, with dataset bias and generation-judge limits documented in the repository.  
[Live demo →](https://fitforge-six.vercel.app) · [Repository →](https://github.com/meetsutariya4448/fitforge) · [RAG evaluation →](https://github.com/meetsutariya4448/fitforge/blob/main/backend/eval/results.md)

---

## 03 / ENGINEERING TOOLKIT

| Layer | Technologies demonstrated in projects |
|---|---|
| **Languages** | Python, Go, JavaScript, SQL |
| **Backend** | FastAPI, SQLAlchemy, Celery, Go `net/http`, REST APIs |
| **AI / Data** | pgvector, sentence-transformers, scikit-learn, RAG, KMeans |
| **Datastores** | PostgreSQL, Redis |
| **Delivery / Ops** | Docker Compose, GitHub Actions, Alembic, Prometheus, Vercel, Render |
| **Product UI** | React, Tailwind CSS, Chart.js, Recharts |

---

## 04 / ENGINEERING EVIDENCE

| System | Evidence in the repository |
|---|---|
| **TalentScope** | [Passing CI with 54 tests](https://github.com/meetsutariya4448/talentscope/actions/runs/30116435731); [600-sample search benchmark](https://github.com/meetsutariya4448/talentscope/blob/main/evals/benchmark.json); deterministic clustering regression coverage |
| **Portcullis** | [Sourced scanner corpus and methodology](https://github.com/meetsutariya4448/portcullis/blob/main/control/evals/corpus/README.md); [precision/recall/cost report](https://github.com/meetsutariya4448/portcullis/blob/main/control/evals/REPORT.md); [gateway overhead benchmark](https://github.com/meetsutariya4448/portcullis/blob/main/bench/results.md) |
| **FitForge** | [Live application](https://fitforge-six.vercel.app); [retrieval and generation evaluation](https://github.com/meetsutariya4448/fitforge/blob/main/backend/eval/results.md); explicit notes on optimistic labels, threshold calibration, and judge resolution |

No contribution counters or generic stats panels here—the project evidence is the stronger signal.

---

## 05 / CURRENT WORKING SET

- **Portcullis:** the explicit next boundary is scanner-to-gateway integration and a real allow/block/log policy layer.
- **FitForge:** the latest work adds the hybrid RAG path and examines where onboarding-derived queries diverge from user intent.
- **TalentScope:** recent hardening made clustering deterministic and benchmark artifacts traceable to a single source of truth.

---

## 06 / CONTACT

If the work involves APIs, data movement, retrieval, or the path from model output to a reliable product, I would like to hear about it. I am open to relevant **2027 software, backend, AI/ML, and data engineering internships**.

<p align="center">
  <a href="https://github.com/meetsutariya4448"><strong>GitHub</strong></a>
  &nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="https://www.linkedin.com/in/meetssutariya"><strong>LinkedIn</strong></a>
  &nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="mailto:meetsutariya5930@gmail.com"><strong>meetsutariya5930@gmail.com</strong></a>
</p>
