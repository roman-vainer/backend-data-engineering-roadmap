# Program v2.1 — Backend + Data Engineering

## Goal

Build a strong **Backend Engineer (.NET) with Data Engineering specialization**.

The program is designed around one progression:

**SQL & Data Modeling → Python → Production Pipelines → Warehouse/Lakehouse → PySpark/Databricks → Azure/DataOps → Integrated Backend + Data System**

The order matters. Tools such as Databricks and Azure are introduced only after the underlying data, pipeline, and architectural concepts are understood.

## Learner baseline

The program assumes the learner is **not a programming beginner** and already has practical familiarity with:

- C# / .NET
- basic ASP.NET/backend concepts
- OOP and general software-development practice
- Git/tooling workflows
- basic relational SQL

This roadmap is therefore a **Data Engineering specialization for a backend-oriented engineer**, not a beginner curriculum for learning backend development from zero.

## Planning model

The program uses rolling-wave planning.

All seven modules have a fixed purpose, time budget, core scope, and Definition of Done. Detailed weekly plans and GitHub Issues are created for the current/next module only, then refined before the next module begins.

This lets later modules reflect actual learning pace and project state without changing the 26-week / 208-hour architecture.

---

## Module 01 — Advanced SQL & Data Modeling

**Weeks 1–4 · 32 hours**

### Learning goals

Move beyond CRUD SQL and understand how relational data is modeled, queried, optimized, protected, and operated under concurrent workloads.

### Core topics

- complex JOIN strategies
- advanced aggregation
- CTE and recursive CTE
- window functions
- subqueries and set operations
- constraints and data integrity
- normalization and deliberate denormalization
- transactions and ACID
- isolation levels
- SQL Server row-versioning concepts: SNAPSHOT and READ_COMMITTED_SNAPSHOT
- locking, blocking, deadlocks, concurrency
- query optimizer concepts
- execution plans
- indexes in SQL Server
- clustered vs nonclustered indexes
- covering indexes and included columns
- statistics and cardinality estimation basics
- SARGability
- SQL Server performance analysis
- OLTP modeling
- analytical modeling
- fact and dimension tables
- Slowly Changing Dimensions
- transition from operational model to analytical model

### Technology focus

**Microsoft SQL Server** is the primary database for the program. Azure SQL is introduced later in the cloud module.

### Project integration

The flagship project should establish or refine its SQL Server operational model here. Artifacts created during the four weeks are cumulative and feed the module review rather than being rebuilt in a one-hour final assignment.

### Outcome

Be able to explain not only what a query returns, but why it performs well or poorly, how data structures affect workload behavior, why concurrency changes correctness, and why operational and analytical systems require different models.

---

## Module 02 — Python for Data Engineering

**Weeks 5–7 · 24 hours**

### Learning goals

Use Python as a practical Data Engineering language without turning it into a second backend specialization.

### Core topics

- Python project structure
- virtual environments and packages
- collections and comprehensions
- functions and modules
- exceptions
- typing
- file handling
- JSON and CSV
- Parquet basics
- HTTP/API access
- logging
- pytest
- database access
- **Pandas as the primary dataframe library for required practice**
- Polars at recognition/comparison level
- clean, testable data-processing code

### Project integration

Build small Python data components against the same operational/project data rather than isolated tutorial datasets whenever practical.

### Outcome

Reach the point where Python data code can be read, written, tested, debugged, and used to implement reliable pipeline components.

---

## Module 03 — ETL/ELT & Production Data Pipelines

**Weeks 8–11 · 32 hours**

### Learning goals

Move from scripts to reliable, reproducible, testable data pipelines.

### Reference flow

**Source → Extract → Transform → Validate → Load → Observe**

### Core topics

- ETL vs ELT
- batch processing
- full vs incremental loads
- CDC concepts
- API, SQL Server, CSV and JSON sources
- idempotency
- retries and retry policies
- checkpoints
- watermarks / change boundaries for batch incremental loading
- replay behavior
- error handling
- duplicate handling
- schema evolution
- data contracts
- validation rules
- backfills
- scheduling concepts
- pipeline testing
- observability
- logging and metrics
- recovery after partial failure

### Required practical path

Implement **one cohesive batch-oriented pipeline** that:

- ingests from the project’s backend/SQL Server boundary or another approved source
- uses an explicit watermark/checkpoint strategy
- can be re-run without unintended duplicates
- has defined replay/backfill behavior
- validates input/output
- records enough operational information to diagnose failure
- demonstrates recovery after a controlled partial failure

No additional CDC/orchestration product is required simply to satisfy this learning goal.

### Outcome

Build pipelines that can fail safely, recover predictably, avoid accidental duplication, and provide enough observability to understand what happened.

---

## Module 04 — Data Warehouse, Lakehouse & Analytics Engineering

**Weeks 12–15 · 32 hours**

### Learning goals

Understand how analytical data platforms are designed and why they differ from transactional backend databases.

### Practical core

- Data Warehouse
- Data Lake
- Lakehouse
- dimensional modeling
- star schema
- fact and dimension tables
- grain
- surrogate keys
- SCD patterns
- bronze / silver / gold architecture
- columnar storage
- partitioning
- Parquet
- analytical transformations
- data quality
- focused dbt fundamentals
- dbt tests, documentation and lineage

### Open Table Formats & Catalogs

The scope is intentionally bounded:

- Parquet as the file-format foundation
- Delta Lake as the **primary practical table-format path**
- schema evolution and time-travel concepts
- metadata management
- Apache Iceberg as a **conceptual comparison**, not a second hands-on specialization
- catalog concepts and interoperability at architecture/awareness level

### dbt scope

dbt is used as a focused SQL-based analytics-engineering exercise for transformations, tests, lineage, and documentation. It is **not** introduced as a second orchestration platform or a competing transformation stack.

### Outcome

Be able to design an analytical platform, choose an appropriate model and storage approach, build a bounded transformation/quality flow, and explain the trade-offs between warehouse, lake, and lakehouse architectures.

---

## Module 05 — PySpark & Databricks

**Weeks 16–19 · 32 hours**

### Learning goals

Apply distributed data-processing concepts after SQL, Python, pipelines, and analytical architecture are already understood.

### Core practical path

- Spark architecture at an engineering level
- Spark DataFrames
- transformations and actions
- lazy evaluation
- partitions
- joins
- aggregations
- shuffle
- Spark SQL
- PySpark
- performance fundamentals
- schema handling
- batch processing
- Delta Lake with Spark
- one production-shaped Databricks workflow

### Secondary/awareness scope

- caching/persistence concepts
- basic streaming concepts
- Databricks workspace/compute/jobs concepts beyond the chosen practical workflow

### Execution environment

The environment is defined at the start of the module:

- early Spark mechanics may be practiced locally when that reduces setup friction
- Databricks practice uses one available workspace/environment
- Azure deployment concerns are deliberately deferred to Module 06

The goal is to learn Spark execution and one coherent Databricks workflow, not every platform feature.

### Outcome

Build and reason about a production-style distributed data workflow, identify common performance problems, and explain the main execution trade-offs.

---

## Module 06 — Azure Data Platform & DataOps

**Weeks 20–23 · 32 hours**

### Learning goals

Move the already-understood architecture into the Microsoft cloud ecosystem and operate it using repeatable engineering practices.

### Minimal end-to-end practical path

The practical implementation should use one coherent path built from a subset of:

- Azure SQL
- Azure Storage / Azure Data Lake Storage Gen2
- Azure Data Factory
- Azure Databricks
- Key Vault for secrets where appropriate
- monitoring/logging
- GitHub Actions for selected CI/CD steps

The exact minimal path is fixed when the module is planned in detail. The objective is one deployable system, not equal-depth mastery of every Azure service.

### DataOps topics

- Git-based workflow
- environments
- configuration management
- secrets management
- automated tests
- CI/CD
- deployment concepts
- monitoring and logging
- access control and security boundaries
- cost awareness
- Docker where it directly supports the chosen path
- basic Infrastructure as Code concepts

### Change management

Practice how database/schema changes, configuration changes, and data-contract changes are versioned and promoted between environments.

### Scope control

The goal is not to become a dedicated DevOps, Terraform, Docker, security, or Azure-platform engineer.

Microsoft Fabric is ecosystem awareness only, not a second core platform.

### Outcome

Deploy, configure, test, monitor, and explain one cloud-based data solution in the Microsoft ecosystem, including how code/configuration/schema changes move between environments.

---

## Module 07 — Integrated Backend + Data Engineering & System Design

**Weeks 24–26 · 24 hours**

### Learning goals

Bring together a system that has already been built incrementally and present it as one coherent backend + data architecture.

This module is **not** the first point where Backend and Data meet.

### Target architecture

```text
ASP.NET API
    ↓
SQL Server / Azure SQL OLTP
    ↓
Ingestion pipeline
    ↓
Azure Data Lake
    ↓
PySpark / Databricks
    ↓
Lakehouse / analytical model
    ↓
Analytics / downstream consumer
```

Engineering workflow:

```text
GitHub → PR → Tests → CI/CD → Azure → Monitoring
```

### System Design topics

- end-to-end data flow
- technology choices and trade-offs
- bottlenecks
- failure scenarios
- recovery strategy
- scaling
- data consistency boundaries
- security boundaries
- observability
- operational vs analytical workloads

### Portfolio engineering

The final system should include:

- architecture diagram
- deployment diagram
- high-quality README
- selected ADRs for important architecture decisions
- documented failure and recovery scenarios
- testing strategy
- monitoring/observability explanation
- selected performance measurements or benchmarks
- clear explanation of major trade-offs

### Outcome

Be able to open the project during an interview and explain the entire system as an engineer: what each component does, why it exists, how data moves, what can fail, how it recovers, and why the chosen architecture is appropriate.

---

# Flagship Project — Incremental Integration Thread

One flagship project evolves throughout the entire program.

The project topic is intentionally **TBD** and will be selected separately. The technical roadmap does not depend on the final domain.

Expected evolution:

1. **Module 01:** relational operational model and SQL Server engineering baseline
2. **Module 02:** Python components that can read/process project data
3. **Module 03:** reliable ingestion with explicit incremental-load and recovery behavior
4. **Module 04:** analytical model and layered/lakehouse representation
5. **Module 05:** distributed processing and Delta/Databricks workflow
6. **Module 06:** Azure deployment, configuration, CI/CD, secrets, and monitoring
7. **Module 07:** integration, hardening, recovery/system-design review, documentation, and presentation

The existing ASP.NET/backend layer is introduced into the integration thread before the final module as the operational system/data boundary. The roadmap does not spend a separate month reteaching beginner backend development.

The objective is a single credible engineering system, not seven unrelated demo projects.

---

# AI-Assisted Engineering — Cross-Cutting Track

AI does **not** receive a separate month.

A practical target is **approximately 30–45 minutes per week of deliberate AI-workflow learning**, embedded inside the existing module budgets. Across 26 weeks this is roughly 13–20 hours. Ordinary AI use during normal implementation is not separately counted.

Examples of deliberate practice:

- task analysis and implementation planning
- comparing implementation options
- unit and integration test generation
- edge-case discovery
- SQL review
- execution-plan analysis support
- refactoring
- debugging
- documentation
- pull-request descriptions
- code review
- GitHub Issues → agent task → changes → PR → review
- repository-level instructions for agents
- multi-file agent workflows
- selective use of MCP and external tools

Principle:

> AI accelerates engineering work; it does not replace understanding, validation, testing, or ownership of the result.

---

# Time Budget

| Module | Weeks | Hours |
|---|---:|---:|
| Advanced SQL & Data Modeling | 4 | 32 |
| Python for Data Engineering | 3 | 24 |
| ETL/ELT & Production Data Pipelines | 4 | 32 |
| Data Warehouse, Lakehouse & Analytics Engineering | 4 | 32 |
| PySpark & Databricks | 4 | 32 |
| Azure Data Platform & DataOps | 4 | 32 |
| Integrated Backend + Data Engineering | 3 | 24 |
| **Total** | **26** | **208** |

AI-assisted engineering time is included inside these 208 hours rather than added on top.
