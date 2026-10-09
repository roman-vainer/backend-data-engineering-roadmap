# Backend + Data Engineering Roadmap

A 26-week, 208-hour self-study program focused on building the profile:

> **Backend Engineer (.NET) with strong Data Engineering skills**

The roadmap deliberately builds a Data Engineering specialization on top of an existing backend/programming foundation instead of treating Backend and Data as two disconnected tracks.

## Learner baseline

This is **not** a beginner programming or beginner backend curriculum.

The program assumes practical familiarity with:

- programming fundamentals and OOP
- C# / .NET
- basic ASP.NET/backend concepts
- Git and normal command-line/tooling workflows
- basic relational SQL

The roadmap deepens the data side of that profile while continuously connecting it back to a .NET backend system.

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
- **Depth over breadth:** one coherent Microsoft-centered path is preferred over collecting unrelated technologies

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

The project domain will be selected separately. The roadmap intentionally does not depend on a specific business topic.

The integration must happen progressively rather than being deferred to Module 07:

1. SQL Server operational model
2. existing ASP.NET/backend boundary connected to transactional data
3. data extraction/ingestion from that operational system
4. reliable incremental pipelines
5. analytical model and layered storage
6. distributed processing
7. Azure deployment and DataOps
8. final integration, recovery analysis, system design, and portfolio presentation

By Module 07, the system should already exist in substantial form. The final module is for integration, validation, hardening, explanation, and presentation — not for building the entire architecture from scratch.

## AI-assisted engineering

AI tools are integrated throughout the full program.

A practical target is **about 30–45 minutes per week of deliberate AI-workflow learning**, embedded inside the existing module time budgets. Across 26 weeks this is roughly 13–20 hours. Ordinary AI use during normal coding is not separately counted.

AI is used for planning, implementation alternatives, test generation, edge-case discovery, SQL review, execution-plan analysis, refactoring, debugging, documentation, pull-request preparation, code review, repository instructions, multi-file agent workflows, and selected external-tool/MCP workflows.

AI output must be reviewed, validated, tested, and understood before it is accepted.

See [ai-engineering/README.md](ai-engineering/README.md).

## Planning model

The roadmap uses **rolling-wave planning**:

- all seven modules have fixed goals, scope, hours, and Definition of Done
- only the current/next module is decomposed into detailed weekly tasks and GitHub Issues
- before a new module starts, its detailed plan is created using what was learned about pace, difficulty, and project state in the previous module

This avoids pretending that every hour of a six-month program can be predicted accurately on day one.

## Repository structure

```text
.
├── README.md
├── ROADMAP.md
├── ai-engineering/
│   └── README.md
├── docs/
│   ├── repository-audit.md
│   └── repository-audit-v2.1.md
└── modules/
    ├── 01-advanced-sql-data-modeling/
    ├── 02-python-data-engineering/
    ├── 03-etl-elt-data-pipelines/
    ├── 04-warehouse-lakehouse-analytics/
    ├── 05-pyspark-databricks/
    ├── 06-azure-data-dataops/
    └── 07-integrated-backend-data/
```

## Tracking

Progress is tracked through **GitHub Milestones and Issues**.

- one Milestone represents one module
- Issues represent concrete learning/work units
- module READMEs define learning paths and completion criteria
- Issues are created in detail only when a module approaches execution

Module 01 already uses this structure; later modules will be decomposed before they start.

## Source of truth

To reduce duplication drift:

- **ROADMAP.md** is the source of truth for overall sequence, module hours, scope, and cross-module architecture
- **module README files** are the source of truth for module-specific learning goals, practice, and Definition of Done
- **GitHub Issues/Milestones** are the source of truth for execution progress
