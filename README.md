# Backend + Data Engineering Roadmap

A 26-week, 208-hour self-study program focused on building the profile:

> **Backend Engineer (.NET) with strong Data Engineering skills**

The roadmap deliberately builds Data Engineering on top of a backend engineering foundation instead of treating the two areas as separate tracks.

## Program principles

- **Duration:** 26 weeks
- **Workload:** ~8 hours per week
- **Total:** 208 hours
- **Primary backend ecosystem:** C# / .NET / ASP.NET
- **Primary database:** Microsoft SQL Server
- **Cloud database context:** Azure SQL
- **Cloud platform:** Microsoft Azure
- **Data platform focus:** SQL Server, Azure SQL, Azure Data Lake Storage, Azure Data Factory, Databricks, PySpark
- **AI tools:** used throughout the program as engineering tools, not as a separate specialization

## Learning sequence

| Module | Weeks | Hours | Focus |
|---|---:|---:|---|
| 01 | 1–4 | 32 | Advanced SQL & Data Modeling |
| 02 | 5–7 | 24 | Python for Data Engineering |
| 03 | 8–11 | 32 | ETL/ELT & Production Data Pipelines |
| 04 | 12–15 | 32 | Data Warehouse, Lakehouse & Analytics Engineering |
| 05 | 16–19 | 32 | PySpark & Databricks |
| 06 | 20–23 | 32 | Azure Data Platform & DataOps |
| 07 | 24–26 | 24 | Integrated Backend + Data Engineering & System Design |

Detailed program: [ROADMAP.md](ROADMAP.md)

## Flagship project

Throughout the 26-week program, a **single flagship project** will be developed incrementally.

Each module will add new architectural, backend, data engineering, cloud, testing, and operational capabilities to the same system. The project domain will be selected separately; the roadmap intentionally does not depend on a specific business topic.

The goal is that by the end of the program the project demonstrates one coherent engineering system rather than a collection of disconnected technology demos.

## AI-assisted engineering

AI tools are integrated into the full program and account for approximately **15–20 hours of the 208 total hours** (~7–10%).

They are used for planning, implementation alternatives, test generation, edge-case discovery, SQL review, execution-plan analysis, refactoring, debugging, documentation, pull-request preparation, code review, repository instructions, multi-file agent workflows, and selected external-tool/MCP workflows.

AI output must be reviewed and understood before it is accepted into the codebase.

## Repository structure

```text
.
├── README.md
├── ROADMAP.md
├── PROGRESS.md
├── ai-engineering/
│   └── README.md
└── modules/
    ├── 01-advanced-sql-data-modeling/
    ├── 02-python-data-engineering/
    ├── 03-etl-elt-data-pipelines/
    ├── 04-warehouse-lakehouse-analytics/
    ├── 05-pyspark-databricks/
    ├── 06-azure-data-dataops/
    └── 07-integrated-backend-data/
```

Milestones, GitHub Issues, weekly tasks, resources, and detailed exercises will be added progressively.
