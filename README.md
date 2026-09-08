## Hey, I'm Hariharan Nadanasabapathi — Hari

**Backend engineer. I build services that handle sensitive data carefully: who's allowed to see what, what happens when a dependency dies, and where every number came from.**

MS Computer Science. Most of my work runs on healthcare data, because that's where the hard parts show up — access control that has to hold at the database level, audit trails that can't be optional, and answers that are confidently wrong instead of loudly broken.

I'd rather ship one system with real numbers than five demos with none.

### Backend

**[Clinical-Evidence-Api](https://github.com/hariharan-sabapathi/Clinical-Evidence-Api)** — Deployed FastAPI service over a clinical FHIR corpus. Authorization enforced by Postgres row-level security, not by checks in route handlers. Async ingestion, audit logging in the same transaction as the read, optimistic locking, circuit breaker. [Live](https://clinical-evidence-api.onrender.com/docs) — log in as one clinician, request another's patient, watch the 403.

**[Real-Time-Subscription-Data-Platform](https://github.com/hariharan-sabapathi/Real-Time-Subscription-Data-Platform)** — Debezium → Kafka → Spark Streaming → Delta Lake → dbt, orchestrated on Airflow. Writing the runbook found four real bugs in my own pipeline. Three are fixed in the history; the fourth is documented with the reason it isn't.

**[FilmIQ](https://github.com/hariharan-sabapathi/FilmIQ---A-Movie-Analytics-System)** — BCNF schema over IMDb and Oscars data, with three before/after `EXPLAIN ANALYZE` cases. One of them is a negative result: the index was structurally correct and moved nothing, because that table was 0.35% of the query's buffer reads.

**[CMS-Hospital-Performance-Platform](https://github.com/hariharan-sabapathi/CMS-Hospital-Performance-Platform)** — Config-driven ingestion → dbt → FastAPI read API, Dockerized with CI. Cursor pagination that doesn't silently drop rows when the sort column is NULL, with a test that proves it. Published the null result honestly: ρ = −0.025 across 1,079 hospitals.

**[Medical-Insurance-Claims-And-Denial-Analytics](https://github.com/hariharan-sabapathi/Medical-Insurance-Claims-And-Denial-Analytics)** — CMS claims star schema with CARC denial modeling and revenue-cycle KPIs. Says plainly which half of each number is real DE-SynPUF data and which half is modeled.

### Retrieval and models

The generation side of the systems above — and where I learned what the serving layer has to survive.

**[ClaimX](https://github.com/hariharan-sabapathi/ClaimX)** — Text-to-SQL on a claims warehouse, QLoRA-tuned. Scored by execution against a gold oracle, not string match. Separates queries that crash from queries that lie. The eval runs as a CI gate.

**[Second-Opinion](https://github.com/hariharan-sabapathi/Second-Opinion)** — Agentic RAG that grades its own retrieval before answering, rewrites the query when it fails, and stops after three rounds.

**[clinical-retrieval](https://github.com/hariharan-sabapathi/clinical-retrieval)** — RAG over 7,761 clinical notes. 194-question eval set, ground truth from structured FHIR, five chunking strategies benchmarked. Reports a lift that *didn't* reach significance.

### Stack

`Python` `FastAPI` `Postgres` `SQL` `Redis` `Docker` `pytest` `GitHub Actions` `pgvector` `Alembic` `PySpark` `Kafka` `dbt` `Airflow` `DuckDB` `Snowflake` `AWS` `PyTorch`

### How I work

Ground truth comes from an independent source or it isn't ground truth. Limitations sections are a feature. If the benchmark hasn't run, the table stays empty. When a number turns out to be an artifact of how I measured it, I say so and publish the smaller one.

📫 [LinkedIn](https://www.linkedin.com/in/hariharan-nadanasabapathi/) · [Portfolio](https://hariharan-sabapathi.github.io/portfolio-website/) · [Email](mailto:hari.sabgee@gmail.com)
