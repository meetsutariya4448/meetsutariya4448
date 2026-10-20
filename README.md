# Meet Sutariya

**Software engineering · Backend & platform · AI / ML & data**

Computer Science undergraduate, Data Science minor at **Arizona State University · 2027**.
I build backend systems, AI applications, and data studies—with tests for how they fail and evidence for what they claim.

[Portfolio](https://meet-sutariya-portfolio.vercel.app) · [LinkedIn](https://www.linkedin.com/in/meetssutariya/) · [Email](mailto:meetsutariya5930@gmail.com)

<p>
  <img src="https://skillicons.dev/icons?i=python" width="32" height="32" alt="Python" />
  <img src="https://skillicons.dev/icons?i=cpp" width="32" height="32" alt="C++" />
  <img src="https://skillicons.dev/icons?i=java" width="32" height="32" alt="Java" />
  <img src="https://skillicons.dev/icons?i=go" width="32" height="32" alt="Go" />
  <img src="https://skillicons.dev/icons?i=ts" width="32" height="32" alt="TypeScript" />
  <img src="https://skillicons.dev/icons?i=postgres" width="32" height="32" alt="PostgreSQL" />
  <img src="https://skillicons.dev/icons?i=docker" width="32" height="32" alt="Docker" />
  <img src="https://skillicons.dev/icons?i=pytorch" width="32" height="32" alt="PyTorch" />
</p>

## 01 / Systems & applications

### [ForgeKV](https://github.com/meetsutariya4448/ForgeKV) — A database from the storage layer up

A C++ key-value server with TCP networking, concurrent requests, and persistent storage. Checksums, crash recovery, and compaction protect stored data; sanitizer and fuzz tests exercise the failure paths. The working server is single-node.

**C++20 · CMake · GoogleTest** · [Architecture](https://github.com/meetsutariya4448/ForgeKV/blob/main/docs/ARCHITECTURE.md) · [Tests & CI](https://github.com/meetsutariya4448/ForgeKV/actions)

### [EventForge](https://github.com/meetsutariya4448/EventForge) — Orders that recover from partial failure

Four services coordinate orders, payments, inventory, and notifications through Kafka. Transactional outboxes prevent lost events, duplicate messages have no duplicate database effect, and failed workflows trigger compensating actions. Fault-injection tests use real PostgreSQL and Kafka.

**Java · Spring Boot · Kafka · PostgreSQL** · [Architecture](https://github.com/meetsutariya4448/EventForge/blob/main/docs/architecture.md) · [Tests & CI](https://github.com/meetsutariya4448/EventForge/actions)

### [TalentScope](https://github.com/meetsutariya4448/talentscope) — Job search by keyword and meaning

Background workers collect and embed job postings. The API combines keyword and vector search, then answers questions with links to the retrieved postings. A controlled local benchmark traces slow inference to CPU thread oversubscription and measures the fix.

**Python · FastAPI · Celery · Redis · PostgreSQL / pgvector** · [Benchmark & limits](https://github.com/meetsutariya4448/talentscope/blob/main/evals/thread-ab.md)

### [Portcullis](https://github.com/meetsutariya4448/portcullis) — One gateway for AI tool servers

A Go gateway routes MCP requests with retries, circuit breakers, and admission checks. A separate Python worker scans tool descriptions before they reach a model. An evaluation audit identified family leakage; I revised the split and withdrew unsupported cascade-quality claims.

**Go · Python · PostgreSQL · OpenTelemetry · Prometheus** · [Architecture](https://github.com/meetsutariya4448/portcullis/blob/main/ARCHITECTURE.md) · [Evaluation & caveats](https://github.com/meetsutariya4448/portcullis/tree/main/control/evals)

### [FitForge](https://github.com/meetsutariya4448/fitforge) — Plan workouts, log sessions, track progress

A fitness app with reference-grounded workout generation and saved training history. The engineering work includes concurrency-safe refresh tokens, runtime API validation, and browser tests. Generation uses onboarding answers and reference documents, not logged workout history.

**TypeScript · React · FastAPI · PostgreSQL · Playwright** · [Screenshots & implementation](https://github.com/meetsutariya4448/fitforge#what-it-looks-like) · [Tests & CI](https://github.com/meetsutariya4448/fitforge/actions)

## 02 / Data, ML & evaluation

These projects ask a specific question, compare against baselines, and report uncertainty and limitations. They are retrospective studies—not live experiments or production ML deployments.

### [GridWatch](https://github.com/meetsutariya4448/GridWatch) — Forecasting when the latest data is late

Forecasts electricity demand under an assumed 24-hour reporting delay. Compares LightGBM, Chronos-2, and simpler baselines, then checks prediction-interval coverage and where forecasts fail.

**Python · LightGBM · Chronos-2 · MLflow** · [Results & reliability](https://github.com/meetsutariya4448/GridWatch/blob/main/reports/reliability_report.md)

### [CivicLens](https://github.com/meetsutariya4448/CivicLens) — What NYC complaint records can tell us

Studies recorded closure times for heat and hot-water complaints using survival analysis. Validates data across DuckDB, local Spark, and Databricks Delta, with S3 transfer checks and a local Tableau dashboard. Recorded closure does not establish that a repair happened.

**SQL · Python · PySpark · Databricks / Delta · Tableau** · [Study & platform evidence](https://github.com/meetsutariya4448/CivicLens#what-ran-where)

### [AuditBudget](https://github.com/meetsutariya4448/AuditBudget) — How much review does AI evaluation need?

Replays limited review budgets using RAGTruth's existing human annotations. Tests whether model-assisted estimates improve precision while keeping uncertainty intervals reliable; reports the small-budget case that fails the coverage requirement.

**Python · scikit-learn · DuckDB · Statistical simulation** · [Findings & limitations](https://github.com/meetsutariya4448/AuditBudget/blob/main/reports/technical_report.md)

### [ExposureRank](https://github.com/meetsutariya4448/ExposureRank) — When offline recommendation rankings change

Trains recommendation baselines and PyTorch models, then tests how missing feedback and sampled candidates change model comparisons. Keeps those two effects separate and retains inconclusive results.

**Python · PyTorch · NumPy · DuckDB** · [Evaluation report](https://github.com/meetsutariya4448/ExposureRank/blob/main/reports/technical_report.md)

### [CampaignLab](https://github.com/meetsutariya4448/CampaignLab) — Does learned targeting beat a simple campaign?

Analyzes a historical email experiment and evaluates a targeting policy on held-out data. The learned policy did not outperform sending the best campaign to everyone—a useful result against unnecessary personalization.

**Python · scikit-learn · statsmodels · DuckDB** · [Decision memo](https://github.com/meetsutariya4448/CampaignLab/blob/main/reports/executive_memo.md)

### [ExperimentGuard](https://github.com/meetsutariya4448/ExperimentGuard) — A/B-test decisions with evidence checks

Analyzes historical headline experiments with validity checks, multiple-comparison controls, and a frozen decision policy. A dashboard explains when the evidence supports a launch and when it is insufficient.

**Python · DuckDB · dbt · SciPy · Streamlit** · [Dashboard](https://experiment-guard-chi.vercel.app) · [Decision rules](https://github.com/meetsutariya4448/ExperimentGuard#the-frozen-statistical-policy)

## 03 / Toolkit

| Area | Tools used in these projects |
| :--- | :--- |
| Languages | Python, C++, Java, Go, TypeScript, SQL |
| Backend | FastAPI, Spring Boot, Kafka, Celery, Redis |
| AI & ML | PyTorch, scikit-learn, LightGBM, embeddings, hybrid retrieval |
| Data | PostgreSQL / pgvector, DuckDB, dbt, PySpark, Databricks / Delta |
| Product | React, Next.js, Streamlit, Tableau |
| Validation & operations | pytest, GoogleTest, Testcontainers, Playwright, Docker, GitHub Actions, OpenTelemetry |

## 04 / How I check my work

- **Test failures deliberately.** Crash recovery in ForgeKV, broker failures in EventForge, and concurrent token redemption in FitForge.
- **Separate development from evaluation.** Locked splits, baseline comparisons, and reproducible reports in the data and ML studies.
- **Keep claims within the evidence.** Local benchmarks stay local; historical findings stay historical; inconclusive and negative results stay in the reports.

Open to **2027 internships** in software, backend, platform/cloud, AI/ML, and data engineering.

[Portfolio](https://meet-sutariya-portfolio.vercel.app) · [LinkedIn](https://www.linkedin.com/in/meetssutariya/) · [Email](mailto:meetsutariya5930@gmail.com)
