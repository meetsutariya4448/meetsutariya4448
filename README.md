<p align="center">
  <img src="./assets/profile-hero.svg" width="100%" alt="Meet Sutariya — distributed systems, platform engineering, and applied AI" />
</p>

<p align="center">
  <a href="https://github.com/meetsutariya4448"><strong>GitHub</strong></a>
  &nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="https://www.linkedin.com/in/meetssutariya"><strong>LinkedIn</strong></a>
  &nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="mailto:meetsutariya5930@gmail.com"><strong>Email</strong></a>
  &nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="https://github.com/meetsutariya4448/fitforge"><strong>FitForge</strong></a>
</p>

---

## 01 / ENGINEERING PROFILE

I am a Computer Science + Data Science undergraduate at Arizona State University, graduating in 2027. My strongest work spans distributed transactions, storage and networking, resilient gateways, data platforms, applied retrieval, and full-stack product engineering—built in C++, Java, Go, Python, and TypeScript.

The common thread is proof: make state and failure boundaries explicit, test the guarantees against real infrastructure, then measure before making a performance claim. I am looking for 2027 AI/ML SWE, platform/cloud SWE, backend, and general software engineering internships where that depth and range are useful.

<table>
  <tr>
    <th align="left">SYSTEMS</th>
    <th align="left">PLATFORM / CLOUD</th>
    <th align="left">AI / DATA</th>
  </tr>
  <tr>
    <td>TCP protocols, concurrent servers, persistence, crash recovery</td>
    <td>Distributed services, Kafka workflows, containers, observability, IaC exercises</td>
    <td>Hybrid retrieval, embeddings, RAG, evaluation, inference performance</td>
  </tr>
</table>

---

## 02 / SELECTED SYSTEMS

### 01 · [EventForge](https://github.com/meetsutariya4448/EventForge)

#### Distributed transactions with failure semantics made explicit.

Four Spring Boot services own separate PostgreSQL databases and coordinate through Kafka. Transactional outboxes remove the database/broker dual write; idempotent consumers absorb redelivery; a persisted saga compensates partial failure; trace context continues across HTTP, outbox relay, and asynchronous consumers.

`Java 21 · Spring Boot · Kafka · PostgreSQL · Testcontainers · OpenTelemetry · Flyway · TypeScript`

**Role signal:** Platform/cloud SWE · backend engineering · distributed systems · Java SWE

**Engineering evidence:** **89 tests** against real PostgreSQL and Kafka · fault injection at commit/ack boundaries · six-job CI green on the current commit · **22 ADRs** documenting system decisions and limits.

[Repository →](https://github.com/meetsutariya4448/EventForge) · [Architecture →](https://github.com/meetsutariya4448/EventForge/blob/main/docs/architecture.md) · [CI →](https://github.com/meetsutariya4448/EventForge/actions/runs/34058193491)

<br>

### 02 · [ForgeKV](https://github.com/meetsutariya4448/ForgeKV)

#### A persistent key-value server built below the framework line.

A versioned binary protocol feeds a bounded TCP server and sharded in-memory index backed by checksummed, append-only segments. The engine handles TTL expiry, compaction, truncated-tail recovery, corruption detection, and process-level ownership of the data directory.

`C++20 · CMake · GoogleTest · TCP · Threads · Sanitizers · libFuzzer · GitHub Actions`

**Role signal:** General SWE · systems engineering · C++ SWE · storage and performance

**Engineering evidence:** **130 tests** passed in each latest Release and sanitizer configuration · two parser fuzzers completed **10,000 runs each** · a focused TCP fix reduced median p99 batch latency from **49.2 ms to 0.99 ms** under the documented loopback benchmark.

[Repository →](https://github.com/meetsutariya4448/ForgeKV) · [Storage format →](https://github.com/meetsutariya4448/ForgeKV/blob/main/docs/STORAGE_FORMAT.md) · [CI →](https://github.com/meetsutariya4448/ForgeKV/actions/runs/34140977502)

<br>

### 03 · [TalentScope](https://github.com/meetsutariya4448/talentscope)

#### A distributed search and retrieval service measured under a fixed CPU budget.

Celery workers ingest and embed job postings into PostgreSQL; FastAPI combines GIN full-text search with pgvector HNSW retrieval through Reciprocal Rank Fusion. Redis coordinates queues, in-flight claims, answer caching, and spend controls, while readiness gates model-backed routes until the per-process encoder is warm.

`Python · FastAPI · PostgreSQL · pgvector · Celery · Redis · sentence-transformers · Docker`

**Role signal:** AI/ML SWE · platform/cloud SWE · backend engineering · data systems

**Engineering evidence:** **171 hosted-CI tests** · fixed-2-CPU A/B testing improved successful throughput from **20.7 to 100.1 req/s** and reduced p95 latency from **9,239 to 665 ms** across ten alternating trials · Kubernetes and Terraform are exercised locally with kind and LocalStack, not claimed as a production cloud deployment.

[Repository →](https://github.com/meetsutariya4448/talentscope) · [Measurement →](https://github.com/meetsutariya4448/talentscope/blob/main/evals/thread-ab.md) · [CI →](https://github.com/meetsutariya4448/talentscope/actions/runs/34140832321)

<br>

### 04 · [Portcullis](https://github.com/meetsutariya4448/portcullis)

#### A resilient MCP gateway with content-bound admission enforcement.

The Go data plane handles protocol validation, legacy translation, safe retries, circuit breaking, bulkheads, backpressure, multi-tenant policy, SSE streaming, failover, metrics, and tracing. Its admission gate reads content-hashed verdicts from PostgreSQL before routing; an out-of-band Python worker scans newly discovered tool descriptions without placing a multi-second classifier on the request path.

`Go · Python · PostgreSQL · net/http · OpenTelemetry · Prometheus · sentence-transformers · Docker`

**Role signal:** Platform SWE · backend engineering · AI infrastructure · security engineering

**Engineering evidence:** native-path added p50 **+0.80 ms** in the documented local benchmark · circuit breaker opened and recovered in **6 seconds** around a real upstream stop/restart · an audit found that the earlier scanner headline depended on near-duplicate family leakage, so the split was rebuilt around held-out families, runs are now fingerprinted, and cascade quality is no longer reported without a complete revised run.

[Repository →](https://github.com/meetsutariya4448/portcullis) · [Architecture →](https://github.com/meetsutariya4448/portcullis/blob/main/ARCHITECTURE.md) · [Results →](https://github.com/meetsutariya4448/portcullis/blob/main/bench/results.md)

<br>

### 05 · [FitForge](https://github.com/meetsutariya4448/fitforge)

#### A full-stack fitness product with concurrency-safe authentication and a typed API boundary.

The React/TypeScript client builds and tracks workout plans through a FastAPI/PostgreSQL backend. Refresh-token redemption is a single conditional database update so concurrent tabs produce one winner; zod validates responses at runtime, and CI checks those schemas against the backend's generated OpenAPI contract. Plan generation retrieves from a ten-document knowledge base with BM25 + vector search fused by RRF; logged workout history is not part of generation.

`TypeScript · React · FastAPI · PostgreSQL · pgvector · SQLAlchemy · Alembic · zod · Playwright · pytest`

**Role signal:** General SWE · full-stack engineering · backend engineering · applied AI

**Engineering evidence:** five green CI jobs on the current commit · **113 backend tests** including real-PostgreSQL integration and eight-thread refresh redemption · **25 component tests** · **17 browser tests** · screenshots and limitations are documented; the hosted demo predates the current build, so local setup is the supported path.

[Repository →](https://github.com/meetsutariya4448/fitforge) · [CI →](https://github.com/meetsutariya4448/fitforge/actions/runs/34169904811) · [Architecture →](https://github.com/meetsutariya4448/fitforge#how-it-works)

### Project index

| # | Project | What it demonstrates |
|---:|---|---|
| 01 | [EventForge](https://github.com/meetsutariya4448/EventForge) | Distributed transactions, failure recovery, Kafka, observability |
| 02 | [ForgeKV](https://github.com/meetsutariya4448/ForgeKV) | C++ systems, TCP, concurrency, storage, profiling |
| 03 | [TalentScope](https://github.com/meetsutariya4448/talentscope) | Data pipelines, hybrid retrieval, resource-aware inference |
| 04 | [Portcullis](https://github.com/meetsutariya4448/portcullis) | Go gateway engineering, resilience, protocol security |
| 05 | [FitForge](https://github.com/meetsutariya4448/fitforge) | Atomic token rotation, typed API contracts, product workflows, CI |

---

## 03 / ENGINEERING TOOLKIT

<p align="center">
  <img src="./assets/toolkit-panel.svg" width="100%" alt="Verified toolkit across systems, platforms, AI and data, operations, and validation" />
</p>

---

## 04 / ENGINEERING EVIDENCE

<p align="center">
  <img src="./assets/evidence-panel.svg" width="100%" alt="Project-specific test, fault-injection, fuzzing, and benchmark evidence" />
</p>

<p align="center">
  <a href="https://github.com/meetsutariya4448/EventForge/actions/runs/34058193491"><strong>EventForge CI</strong></a>
  &nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="https://github.com/meetsutariya4448/ForgeKV/actions/runs/34140977502"><strong>ForgeKV CI</strong></a>
  &nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="https://github.com/meetsutariya4448/talentscope/actions/runs/34140832321"><strong>TalentScope CI</strong></a>
  &nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="https://github.com/meetsutariya4448/fitforge/actions/runs/34169904811"><strong>FitForge CI</strong></a>
  &nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="https://github.com/meetsutariya4448/portcullis/blob/main/control/evals/REPORT.md"><strong>Portcullis evaluation</strong></a>
</p>

The numbers above are repository-specific and methodology-linked. Local benchmarks are not presented as production capacity, and local kind/LocalStack exercises are not presented as a cloud deployment.

---

## 05 / CURRENT WORKING SET

- **Portcullis:** enforcing content-bound scanner verdicts while keeping evaluation splits leakage-resistant and reproducible.
- **FitForge:** tightening authentication races, runtime response validation, browser behavior, and frontend/backend contract checks.
- **TalentScope:** operating the retrieval service under explicit CPU, readiness, recovery, spend, and infrastructure constraints.

---

## 06 / CONTACT

I am interested in teams that care about system boundaries, measurable behavior, and software that survives more than the happy path. I am open to relevant **2027 AI/ML SWE, platform/cloud SWE, backend, and general software engineering internships**.

<p align="center">
  <a href="https://github.com/meetsutariya4448"><strong>GitHub</strong></a>
  &nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="https://www.linkedin.com/in/meetssutariya"><strong>LinkedIn</strong></a>
  &nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="mailto:meetsutariya5930@gmail.com"><strong>meetsutariya5930@gmail.com</strong></a>
</p>
