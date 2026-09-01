## Hey, I’m Hariharan Nadanasabapathi! Let’s keep it simple — Hari

**AI engineer.** Retrieval systems, tool-using agents, domain-adapted models — and the data infrastructure they sit on.

MS Computer Science. Most of my work runs on real healthcare data, because that's where retrieval gets hard: repetitive corpora, business rules that live outside the schema, and answers that are confidently wrong instead of loudly broken.

I'd rather ship one system with real numbers than five demos with none.

### Building

**[clinical-retrieval](https://github.com/hariharan-sabapathi/clinical-retrieval)** — RAG over 7,761 clinical notes. 194-question eval set, ground truth from structured FHIR, five chunking strategies benchmarked. Reports a lift that *didn't* reach significance.

**[ClaimX](https://github.com/hariharan-sabapathi/ClaimX)** — Text-to-SQL on a claims warehouse, QLoRA-tuned. Scored by execution accuracy against a gold oracle, not string match. Separates queries that crash from queries that lie.

**[Second-Opinion](https://github.com/hariharan-sabapathi/Second-Opinion)** — Agentic RAG that grades its own retrieval before answering, rewrites the query when it fails, and stops after three rounds.

**[rag-reads-sees-hears](https://github.com/hariharan-sabapathi/rag-reads-sees-hears)** — Multimodal RAG. Retrieves on descriptions, then re-attaches the original video or audio so the model looks again instead of reading its own summary.

**[Finance-Intelligence-Agent](https://github.com/hariharan-sabapathi/Finance-Intelligence-Agent)** — Five tools do the math in SQL. The model only picks which one. Every number traces to a row.

**[HiNet](https://github.com/hariharan-sabapathi/HiNet)** — ICCV 2021 invertible image-hiding net, extended with a differentiable noise layer. [Live demo](https://nexus-hinet-app.streamlit.app/).

### Underneath

**[CMS-Hospital-Performance-Platform](https://github.com/hariharan-sabapathi/CMS-Hospital-Performance-Platform)** — Config-driven ingestion → dbt → FastAPI, Dockerized with CI. Found a join bug, fixed it, then published the null result honestly: ρ = −0.025 across 1,079 hospitals.

**[Real-Time-Subscription-Data-Platform](https://github.com/hariharan-sabapathi/Real-Time-Subscription-Data-Platform)** — Debezium → Kafka → Spark Streaming → Delta Lake → dbt, on Airflow, all in Docker.

**[Medical-Insurance-Claims-And-Denial-Analytics](https://github.com/hariharan-sabapathi/Medical-Insurance-Claims-And-Denial-Analytics)** — CMS claims star schema with CARC denial modeling. The warehouse ClaimX queries.

### Stack

`Python` `FastAPI` `PyTorch` `QLoRA` `LangGraph` `ChromaDB` `BM25` `DuckDB` `Postgres` `Docker` `PySpark` `Kafka` `dbt` `Snowflake` `Airflow` `AWS`

### How I work

Ground truth comes from an independent source or it isn't ground truth. Limitations sections are a feature. If the benchmark hasn't run, the table stays empty.

📫 [LinkedIn](https://www.linkedin.com/in/hariharan-nadanasabapathi/) · [Portfolio](https://hariharan-sabapathi.github.io/portfolio-website/) · [Email](mailto:hari.sabgee@gmail.com)
