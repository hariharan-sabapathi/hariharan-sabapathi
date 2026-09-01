## Hari — Hariharan Nadanasabapathi

I build AI systems: retrieval pipelines, tool-using agents, and domain-adapted models — with the data engineering underneath them that most of those systems quietly need.

MS in Computer Science. Most of my work runs on real healthcare data — FHIR bulk exports, CMS claims and quality reporting — because that's where retrieval and evaluation get genuinely hard: the corpus is repetitive, the business definitions live outside the schema, and a plausible wrong answer is worse than a crash.

I care more about whether a system is *measured* than whether it demos well. Several of the repos below report null results, unrun benchmarks, and failure modes on purpose.

---

### AI systems

| Project | What it is |
|---|---|
| **[clinical-retrieval](https://github.com/hariharan-sabapathi/clinical-retrieval)** | RAG over 7,761 synthetic clinical notes. Five chunking strategies benchmarked against each other, patient-aware filtering, and a 194-question eval set whose ground truth is computed from structured FHIR — independent of the note text being searched. Results reported with confidence intervals and paired significance tests, including a lift that didn't reach significance. |
| **[ClaimX](https://github.com/hariharan-sabapathi/ClaimX)** | Text-to-SQL over a healthcare claims warehouse, QLoRA-tuned on Qwen2.5-1.5B. Scored by *execution accuracy* against a gold oracle backend, not string similarity, with a failure taxonomy that separates queries that crash from queries that return a confident wrong number. Read-only execution guard, FastAPI + Gradio. |
| **[Second-Opinion](https://github.com/hariharan-sabapathi/Second-Opinion)** | Self-reflective agentic RAG. A LangGraph loop grades its own retrieval before generating, rewrites the query on a failed grade, and answers anyway after three rounds rather than looping forever. |
| **[rag-reads-sees-hears](https://github.com/hariharan-sabapathi/rag-reads-sees-hears)** | Multimodal RAG. Media is described at ingest so it can be embedded, then the original file is re-attached at query time so the model looks again instead of reading its own earlier summary. |
| **[Finance-Intelligence-Agent](https://github.com/hariharan-sabapathi/Finance-Intelligence-Agent)** | Tool-using agent over a bank export. Five tools do the arithmetic in SQL and pandas; the model only decides which one answers the question. Every figure traces to a row. |
| **[Driver-Behavior-Classification](https://github.com/hariharan-sabapathi/Driver-Behavior-Classification)** | ResNet50 on distracted-driver images, evaluated leave-one-driver-out so the model can't score well by memorizing a driver's seat position. |
| **[HiNet](https://github.com/hariharan-sabapathi/HiNet)** | Refactored ICCV 2021 invertible image-hiding network, extended with a differentiable noise layer so the model trains through JPEG, blur, and resize distortions. [Live demo](https://nexus-hinet-app.streamlit.app/). |

### Data and platform work underneath

| Project | What it is |
|---|---|
| **[CMS-Hospital-Performance-Platform](https://github.com/hariharan-sabapathi/CMS-Hospital-Performance-Platform)** | Two CMS datasets through one config-driven loader into a dbt warehouse (DuckDB local, Snowflake documented), served by a FastAPI read API. Dockerized with CI. Finds and fixes a hospital-ID join bug, then reports the headline analysis as the null result it is: ρ = −0.025, p = 0.40 across 1,079 hospitals. |
| **[Real-Time-Subscription-Data-Platform](https://github.com/hariharan-sabapathi/Real-Time-Subscription-Data-Platform)** | CDC from Postgres via Debezium → Kafka → Spark Structured Streaming → Delta Lake → dbt, orchestrated with Airflow, fully containerized. |
| **[Medical-Insurance-Claims-And-Denial-Analytics](https://github.com/hariharan-sabapathi/Medical-Insurance-Claims-And-Denial-Analytics)** | CMS DE-SynPUF claims into a star schema with CARC denial-reason and preventability modeling. The warehouse ClaimX queries. |
| **[EHR-Data-Integration-And-Patient-Flow-Analytics](https://github.com/hariharan-sabapathi/EHR-Data-Integration-And-Patient-Flow-Analytics)** | FHIR R4 bulk ingestion in PySpark into a dimensional model with length-of-stay, readmission, and throughput analytics. |
| **[Blood-Supply-Intelligence-Platform](https://github.com/hariharan-sabapathi/Blood-Supply-Intelligence-Platform)** | Kafka → Spark Structured Streaming → medallion Delta Lake on S3 for blood inventory and demand events. |

---

### Stack

**AI/ML** — PyTorch, Keras, Hugging Face, PEFT/QLoRA, LangGraph, LangChain, BM25, ChromaDB, embeddings, evaluation harness design
**Backend** — Python, FastAPI, Pydantic, DuckDB, PostgreSQL, SQLite, Docker, GitHub Actions
**Data** — PySpark, Kafka, Debezium, Delta Lake, dbt, Snowflake, Airflow, AWS S3, dimensional modeling

### How I work

- Ground truth comes from a source independent of the thing being tested, or it isn't ground truth.
- A result that didn't reach significance gets reported as not reaching significance.
- READMEs state what the system can't do, what it costs, and where it's wrong at the edges — a limitations section is a feature.
- If a benchmark hasn't been run, the table stays empty rather than getting plausible-looking numbers.

---

📫 [LinkedIn](ADD_YOUR_LINKEDIN_URL) · [Portfolio](ADD_YOUR_PORTFOLIO_URL) · [email](mailto:ADD_YOUR_EMAIL)
