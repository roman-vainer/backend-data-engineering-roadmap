# Program v2.0 — Backend + Data Engineering

## Goal

Build a strong **Backend Engineer (.NET) with Data Engineering specialization**.

The program is designed around one progression:

**SQL & Data Modeling → Python → Production Pipelines → Warehouse/Lakehouse → PySpark/Databricks → Azure/DataOps → Integrated Backend + Data System**

The order matters. Tools such as Databricks and Azure are introduced only after the underlying data, pipeline, and architectural concepts are understood.

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
- locking, blocking, deadlocks, concurrency
- query optimizer concepts
- execution plans
- indexes in SQL Server
- clustered vs nonclustered indexes
- covering indexes and included columns
- statistics and cardinality estimation basics
- SQL Server performance analysis
- OLTP modeling
- analytical modeling
- fact and dimension tables
- Slowly Changing Dimensions
- transition from operational model to analytical model

### Technology focus

**Microsoft SQL Server** is the primary database for the program. Azure SQL is introduced later in the cloud module.

### Outcome

Be able to explain not only what a query returns, but why it performs well or poorly, how data structures affect workload behavior, and why operational and analytical systems require different models.

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
- Pandas basics
- Polars basics
- clean, testable data-processing code

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

### Outcome

Build pipelines that can fail safely, recover predictably, avoid accidental duplication, and provide enough observability to understand what happened.

---

## Module 04 — Data Warehouse, Lakehouse & Analytics Engineering

**Weeks 12–15 · 32 hours**

### Learning goals

Understand how analytical data platforms are designed and why they differ from transactional backend databases.

### Core topics

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
- dbt fundamentals
- dbt tests, documentation and lineage

### Open Table Formats & Catalogs

- Parquet as the file-format foundation
- Delta Lake concepts and practical use
- Apache Iceberg concepts
- Delta Lake vs Apache Iceberg
- schema evolution
- time travel concepts
- metadata management
- catalog concepts
- interoperability between formats and processing engines

### Outcome

Be able to design an analytical platform, choose an appropriate model and storage approach, and explain the trade-offs between warehouse, lake, and lakehouse architectures.

---

## Module 05 — PySpark & Databricks

**Weeks 16–19 · 32 hours**

### Learning goals

Apply distributed data-processing concepts after SQL, Python, pipelines, and analytical architecture are already understood.

### Core topics

- Spark architecture at an engineering level
- Spark DataFrames
- transformations and actions
- lazy evaluation
- partitions
- joins
- aggregations
- shuffle
- caching/persistence concepts
- Spark SQL
- PySpark
- performance fundamentals
- schema handling
- batch processing
- basic streaming concepts
- Delta Lake with Spark
- schema evolution in practice
- Databricks workspace and compute concepts
- notebooks vs production code
- jobs/workflows concepts

### Outcome

Build and reason about a production-style distributed data workflow instead of treating Databricks as a collection of UI features.

---

## Module 06 — Azure Data Platform & DataOps

**Weeks 20–23 · 32 hours**

### Learning goals

Move the locally understood architecture into the Microsoft cloud ecosystem and operate it using repeatable engineering practices.

### Core platform

- Azure SQL
- Azure Storage
- Azure Data Lake Storage Gen2
- Azure Data Factory
- Azure Databricks
- Azure Key Vault concepts
- monitoring and logging services

### DataOps

- Git-based workflow
- environments
- configuration management
- secrets management
- automated tests
- GitHub Actions
- CI/CD
- Docker
- deployment concepts
- monitoring
- access control
- security boundaries
- cost awareness
- basic Infrastructure as Code concepts

### Scope control

The goal is not to become a dedicated DevOps or Terraform engineer. Infrastructure automation is learned to the level required to build and operate a data platform responsibly.

Microsoft Fabric may be reviewed conceptually for ecosystem awareness, but it is not a second core platform in this roadmap.

### Outcome

Deploy, configure, test, monitor, and explain a cloud-based data solution in the Microsoft ecosystem.

---

## Module 07 — Integrated Backend + Data Engineering & System Design

**Weeks 24–26 · 24 hours**

### Learning goals

Combine backend engineering and data engineering into one coherent system and one coherent professional profile.

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

The final system should also include:

- architecture diagram
- deployment diagram
- high-quality README
- ADRs for important architecture decisions
- documented failure scenarios
- testing strategy
- monitoring/observability explanation
- selected performance measurements or benchmarks
- clear explanation of major trade-offs

### Outcome

Be able to open the project during an interview and explain the entire system as an engineer: what each component does, why it exists, how data moves, what can fail, how it recovers, and why the chosen architecture is appropriate.

---

# Flagship Project

One flagship project will evolve throughout the whole program.

The project topic is intentionally **TBD** and will be selected separately. The technical roadmap does not depend on the final domain.

Expected evolution:

1. relational operational model
2. backend-accessible transactional data
3. ingestion
4. repeatable pipelines
5. analytical model
6. lakehouse layer
7. distributed processing
8. cloud deployment
9. testing and CI/CD
10. monitoring and system-design documentation

The objective is a single credible engineering system, not seven unrelated demo projects.

---

# AI-Assisted Engineering — Cross-Cutting Track

AI does **not** receive a separate month.

Approximately **15–20 hours** of the 208-hour program are intentionally allocated to improving AI-assisted engineering workflows, with additional natural usage during normal development.

Practical scenarios include:

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
