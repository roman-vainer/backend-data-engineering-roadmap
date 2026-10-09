# Module 07 — Integrated Backend + Data Engineering & System Design

**Weeks:** 24–26  
**Time:** 24 hours

## Learning Goals

Integrate, harden, validate, and present the backend + data system that has been built incrementally during Modules 01–06.

This module is **not** the first time Backend and Data are connected.

## Target Flow

**ASP.NET API → SQL Server/Azure SQL OLTP → ingestion → Azure Data Lake → PySpark/Databricks → Lakehouse/analytical model → downstream consumer**

## Topics

End-to-end data flow, trade-offs, bottlenecks, failure scenarios, recovery, scaling, consistency boundaries, security boundaries, observability, operational vs analytical workloads.

## Capstone Scope

The 24 hours are used primarily for:

- integration gaps
- end-to-end validation
- failure/recovery scenarios
- system-design reasoning
- selected performance checks
- architecture documentation
- portfolio presentation

The module must not assume that the API, pipeline, lakehouse, and Azure deployment are all being created from scratch here.

## Portfolio Engineering

Architecture diagram, deployment diagram, high-quality README, selected ADRs, testing strategy, failure/recovery scenarios, monitoring explanation, selected measurements/benchmarks, and documented trade-offs.

## Definition of Done

The module is complete when the learner can present the entire system as an engineer: why each component exists, how data flows, what can fail, how the system recovers, which boundaries matter, and which trade-offs drove the architecture.

## Planning

The detailed weekly plan and Issues are created shortly before this module begins.
