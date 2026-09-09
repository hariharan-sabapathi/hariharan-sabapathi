## Hey, I'm Hariharan Nadanasabapathi — Hari

**Backend engineer. I build services that handle sensitive data carefully: who's allowed to see what, what happens when a dependency dies, and where every number came from.**

MS in Computer Science. Most of my work focuses on healthcare data because that's where the real challenges show up — keeping data secure, tracking changes, and making sure systems give accurate answers.

I'd rather ship one system with real numbers than five demos with none.

### Backend

**[Clinical-Evidence-Api](https://github.com/hariharan-sabapathi/Clinical-Evidence-Api)** — Deployed FastAPI service for securely searching clinical FHIR data, with PostgreSQL-enforced access controls, audit logging, and reliable data processing. [Live](https://clinical-evidence-api.onrender.com/docs) — sign in as one clinician, request another clinician’s patient, and see the database enforce the boundary with a 403.

**[Real-Time-Subscription-Data-Platform](https://github.com/hariharan-sabapathi/Real-Time-Subscription-Data-Platform)** — Debezium → Kafka → Spark Streaming → Delta Lake → dbt, orchestrated on Airflow. Writing the runbook found four real bugs in my own pipeline. Three are fixed in the history; the fourth is documented with the reason it isn't.

**[FilmIQ](https://github.com/hariharan-sabapathi/FilmIQ---A-Movie-Analytics-System)** — Normalized IMDb and Oscars database with `EXPLAIN ANALYZE` testing. Three before/after cases, including an index that made no difference because the table contributed just 0.35% of buffer reads.

**[CMS-Hospital-Performance-Platform](https://github.com/hariharan-sabapathi/CMS-Hospital-Performance-Platform)** — Config-driven ingestion → dbt → FastAPI, Dockerized with CI. Built cursor pagination that handles NULL sort values without dropping rows, backed by tests. Published the result honestly: ρ = −0.025 across 1,079 hospitals.

**[Medical-Insurance-Claims-And-Denial-Analytics](https://github.com/hariharan-sabapathi/Medical-Insurance-Claims-And-Denial-Analytics)** — CMS claims star schema with CARC denial modeling and revenue-cycle KPIs. Clearly separates real DE-SynPUF data from modeled results.

### Retrieval and models

Models can answer the question; the backend has to make sure the whole system works.

**[ClaimX](https://github.com/hariharan-sabapathi/ClaimX)** — QLoRA-tuned Text-to-SQL system for a claims warehouse. Evaluated by executing queries against a gold oracle, not by string matching. Separates queries that crash from queries that return wrong answers, with evaluation enforced in CI.

**[Second-Opinion](https://github.com/hariharan-sabapathi/Second-Opinion)** — Agentic RAG that evaluates its own retrieval before answering, rewrites the query when retrieval fails, and stops after three rounds.

**[clinical-retrieval](https://github.com/hariharan-sabapathi/clinical-retrieval)** — RAG over 7,761 clinical notes, evaluated on 194 questions with ground truth from structured FHIR. Five chunking strategies benchmarked. Reports a lift that *didn't* reach significance.

### Stack
 
`Python` `FastAPI` `Postgres` `SQL` `Redis` `Docker` `GitHub Actions` `PySpark` `Kafka` `dbt` `Delta Lake` `DuckDB` `Snowflake` `AWS` `PyTorch` `Power BI`

### How I work

Ground truth comes from an independent source. Limitations are part of the work. If a benchmark hasn’t run, the table stays empty. If a number is wrong, I say so and use the corrected one.

📫 [LinkedIn](https://www.linkedin.com/in/hariharan-nadanasabapathi/) · [Portfolio](https://hariharan-sabapathi.github.io/portfolio-website/) · [Email](mailto:hari.sabgee@gmail.com)
