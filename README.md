## Hi, I'm Hari (Hariharan Nadanasabapathi)

**Software engineer, data. I build pipelines and backend services for sensitive data: who's allowed to see what, what happens when a dependency dies, and where every number came from.**

M.S. in Computer Science (University at Buffalo, 2026). Currently a Data Research Analyst at UB's Spatial AI & Robotics Lab, building ingestion and validation for multi-modal sensor data. Before that, 1.5 years building Python and SQL pipelines in industry.

Most of my work is in healthcare data, because that's where the hard problems are: keeping data private, tracking what changed, and making sure the answer is actually right.

I'd rather ship one system with real numbers than five demos with none.

### Healthcare data

**[Clinical-Evidence-Api](https://github.com/hariharan-sabapathi/Clinical-Evidence-Api)**: Deployed FastAPI service for searching clinical FHIR data, with access control enforced by PostgreSQL Row-Level Security, an audit record for every read, and 140 tests. [Live](https://clinical-evidence-api.onrender.com/docs): sign in as one clinician, request another clinician's patient, and watch the database refuse with a 403.

**[EHR-Data-Integration-And-Patient-Flow-Analytics](https://github.com/hariharan-sabapathi/EHR-Data-Integration-And-Patient-Flow-Analytics)**: FHIR R4 bulk export → PySpark → a star schema that runs on Snowflake or DuckDB from the same DDL (7,761 encounters, 70,704 LOINC-coded observations), with dbt models for length of stay and readmissions. Flags that the raw ~65% readmission rate is wrong without an inpatient-only denominator.

**[CMS-Hospital-Performance-Platform](https://github.com/hariharan-sabapathi/CMS-Hospital-Performance-Platform)**: Config-driven ingestion → dbt → FastAPI, Dockerized with CI. Traced a silent ID type conversion that was dropping hospitals from joins (now 2,451 of 2,455 match), and built cursor pagination that handles NULL sort values without losing rows. Published the result honestly: ρ = −0.025 (p = 0.40) across 1,079 hospitals.

**[Medical-Insurance-Claims-And-Denial-Analytics](https://github.com/hariharan-sabapathi/Medical-Insurance-Claims-And-Denial-Analytics)**: CMS claims star schema with CARC denial modeling and revenue-cycle KPIs. Keeps real DE-SynPUF data clearly separate from modeled results.

### Pipelines and databases

**[Real-Time-Subscription-Data-Platform](https://github.com/hariharan-sabapathi/Real-Time-Subscription-Data-Platform)**: Debezium → Kafka → Spark Streaming → Delta Lake → dbt, orchestrated on Airflow. Testing it and writing the runbook surfaced four real issues, including invoice amounts that were silently NULL on every row. Three are fixed in the history; the fourth is documented with the reason it isn't.

**[FilmIQ](https://github.com/hariharan-sabapathi/FilmIQ---A-Movie-Analytics-System)**: Normalized IMDb and Oscars database tuned with `EXPLAIN ANALYZE`, from 31 ms to under 0.14 ms. Three before/after cases, including an index that made no difference because its table was just 0.35% of buffer reads.

### Retrieval and models

Models can answer the question; the backend has to make sure the whole system works.

**[clinical-retrieval](https://github.com/hariharan-sabapathi/clinical-retrieval)**: Retrieval over 7,761 clinical notes, evaluated on 194 questions with ground truth from structured FHIR. Five chunking strategies benchmarked; 512-word windows raised strict Recall@5 from 0.414 to 0.724. Reports a lift that *didn't* reach significance.

**[ClaimX](https://github.com/hariharan-sabapathi/ClaimX)**: Text-to-SQL for a claims warehouse, with a QLoRA fine-tuning pipeline and an evaluator that executes queries rather than string-matching them. It separates SQL that crashes from SQL that runs but answers wrong, and CI guards the harness. Model results stay empty until a real run exists.

**[Second-Opinion](https://github.com/hariharan-sabapathi/Second-Opinion)**: Agentic RAG that grades its own retrieval before answering, rewrites the query when retrieval fails, and stops after three rounds.

### Stack

`Python` `SQL` `FastAPI` `PostgreSQL` `Redis` `Docker` `GitHub Actions` `PySpark` `Kafka` `Airflow` `dbt` `Delta Lake` `Snowflake` `DuckDB` `AWS` `FHIR` `PyTorch` `Power BI`

### How I work

Ground truth comes from an independent source. Limitations are part of the work. If a benchmark hasn't run, the table stays empty. If a number is wrong, I say so and use the corrected one.

**Open to:** Software Engineer, Data Engineer and Healthcare Data Engineer roles · Frisco, TX · open to relocation

📫 [LinkedIn](https://www.linkedin.com/in/hariharan-nadanasabapathi/) · [Portfolio](https://hariharan-sabapathi.github.io/portfolio-website/) · [Email](mailto:hari.sabgee@gmail.com)
