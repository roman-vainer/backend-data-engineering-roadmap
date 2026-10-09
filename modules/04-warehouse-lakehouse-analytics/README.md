# Module 04 — Data Warehouse, Lakehouse & Analytics Engineering

**Weeks:** 12–15  
**Time:** 32 hours

## Learning Goals

Understand how analytical platforms differ from transactional systems and how data should be modeled, stored, transformed, and governed for analytics.

## Practical Core

Data Warehouse, Data Lake, Lakehouse, star schema, facts/dimensions, grain, SCD, bronze/silver/gold, Parquet, partitioning, columnar storage, transformations, tests, lineage, documentation, and data quality.

## dbt Scope

dbt is used at a focused fundamentals level for:

- SQL-based transformations
- tests
- documentation
- lineage

It is not treated as a second orchestration platform or a competing end-to-end transformation stack.

## Open Table Formats & Catalogs

- Parquet foundations
- **Delta Lake as the primary hands-on table-format path**
- schema evolution and time-travel concepts
- metadata concepts
- Apache Iceberg as architectural comparison/awareness
- Delta Lake vs Iceberg trade-offs
- catalog concepts
- interoperability at conceptual/architecture level

The goal is to understand the open-table-format landscape without trying to become hands-on expert in two formats within 32 hours.

## Practice

Design an analytical model and implement a bounded layered transformation/quality flow. The model should continue from the project’s operational/incremental data rather than starting a disconnected demo.

## Definition of Done

The module is complete when the learner can justify warehouse/lake/lakehouse choices, model analytical data at the correct grain, implement a practical Delta-oriented layered flow, explain Delta vs Iceberg at a useful engineering level, and build documented/tested transformations.

## Planning

The detailed weekly plan and Issues are created shortly before this module begins.
