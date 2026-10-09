# Module 01 — Advanced SQL & Data Modeling

**Weeks:** 1–4  
**Time:** 32 hours  
**Primary database:** Microsoft SQL Server  
**Cloud continuation:** Azure SQL in Module 06

## Purpose

This module builds the data foundation for the whole roadmap. The goal is not simply to write correct SQL, but to understand how SQL Server executes queries, how relational structures behave under load, how concurrency affects correctness, and how operational models differ from analytical models.

By the end of the module, SQL should be treated as an engineering discipline rather than only as a persistence layer behind EF Core.

## Learning Goals

By the end of Module 01, the learner should be able to:

- write and reason about non-trivial SQL queries
- use JOINs, set operators, CTEs, recursive CTEs, aggregations and window functions confidently
- read actual execution plans and connect estimates to statistics/cardinality
- explain and justify SQL Server indexing choices
- understand SARGability at a practical level
- reason about transactions, isolation levels and concurrency anomalies
- distinguish locking-based READ COMMITTED from SQL Server row-versioning options such as READ_COMMITTED_SNAPSHOT and SNAPSHOT
- reproduce blocking and deadlock scenarios and explain mitigation strategies
- design a normalized OLTP model with appropriate constraints
- derive an analytical star schema from an operational model
- explain grain, facts, dimensions and Slowly Changing Dimensions

---

# Week 1 — Advanced SQL Querying

**Time budget: 8 hours**

## Focus

Move beyond CRUD-style SQL and become comfortable expressing complex data questions clearly and efficiently.

### 1. SQL Server learning environment — 0.5 h

- prepare the local SQL Server environment
- create/import a reusable training database
- establish a baseline folder/script structure for module exercises

### 2. Advanced JOINs and set operations — 1.5 h

- INNER / LEFT / RIGHT / FULL joins
- self joins
- CROSS JOIN and Cartesian-product risks
- UNION / UNION ALL
- INTERSECT
- EXCEPT
- choosing between joins and set operations

### 3. Advanced aggregation — 1.5 h

- GROUP BY beyond basic CRUD reporting
- HAVING
- conditional aggregation
- multi-level aggregation patterns
- GROUPING SETS / ROLLUP / CUBE concepts

### 4. CTE and recursive CTE — 1.5 h

- readable decomposition of complex queries
- multiple CTEs
- recursion anchor and recursive member
- hierarchy traversal
- recursion limits and common mistakes

### 5. Window functions — 2.5 h

- OVER
- PARTITION BY
- ORDER BY inside windows
- ROW_NUMBER / RANK / DENSE_RANK
- LAG / LEAD
- running totals
- moving calculations
- FIRST_VALUE / LAST_VALUE concepts
- combining window functions with aggregations

### 6. Weekly review — 0.5 h

- solve a mixed query task without step-by-step guidance
- explain why the chosen SQL shape is appropriate

### Week 1 outcome

Given a non-trivial data question, the learner can choose an appropriate SQL pattern instead of solving everything with nested CRUD-style queries.

---

# Week 2 — SQL Server Performance & Query Optimization

**Time budget: 8 hours**

## Focus

Understand why a query is fast or slow and how SQL Server decides how to execute it.

### 1. Index architecture — 1.5 h

- clustered indexes
- nonclustered indexes
- composite indexes
- key-column order
- included columns
- covering indexes
- selectivity
- write-cost trade-offs

### 2. Execution plans, estimates & statistics — 2.5 h

- estimated vs actual execution plan
- table scan
- index scan
- index seek
- key lookup
- nested loops
- hash match
- merge join
- sorts
- warning signs and expensive operators
- why statistics matter
- estimated vs actual rows
- cardinality-estimation concepts

### 3. SARGability — 1.0 h

- predicates that prevent efficient index use
- functions on indexed columns
- implicit conversions
- common SARGability patterns

### 4. Query-tuning lab — 2.0 h

- establish a baseline
- inspect execution plan
- compare estimates with actual behavior
- identify the bottleneck
- change query/index design
- compare before/after behavior
- explain the trade-off rather than only reporting that one query became faster

### 5. AI-assisted SQL review — 0.5 h

Use an AI coding assistant on one deliberately imperfect query:

- request review and optimization hypotheses
- validate every suggestion with SQL Server evidence
- reject suggestions that are not supported by the execution plan or measured behavior

### 6. Weekly review — 0.5 h

Explain one tuning case from problem to evidence to solution.

### Week 2 outcome

The learner can inspect an actual execution plan, interpret important estimated/actual differences, recognize common access patterns, propose a justified optimization, and verify whether it actually helped.

---

# Week 3 — Transactions, Isolation & Concurrency

**Time budget: 8 hours**

## Focus

Understand correctness when multiple operations and users access the same data concurrently.

### 1. Transactions and ACID — 1.5 h

- transaction boundaries
- COMMIT / ROLLBACK
- atomicity, consistency, isolation, durability
- error handling around transactions
- why long-running transactions are dangerous

### 2. Isolation levels and anomalies — 2.0 h

- dirty reads
- non-repeatable reads
- phantom reads
- lost-update concepts
- READ UNCOMMITTED
- READ COMMITTED
- REPEATABLE READ
- SERIALIZABLE
- SQL Server row-versioning concepts
- READ_COMMITTED_SNAPSHOT
- SNAPSHOT isolation

### 3. Locking and blocking — 1.5 h

- shared and exclusive locks
- lock duration
- blocking chains
- practical impact of indexes on locking behavior
- contrast locking behavior with row-versioned reads where appropriate

### 4. Deadlocks — 1.0 h

- how deadlocks occur
- deadlock victim
- consistent resource-access order
- transaction-size and indexing considerations

### 5. Concurrency lab — 1.5 h

Use two concurrent SQL sessions to reproduce and document:

- blocking
- at least one isolation anomaly
- a deadlock or controlled deadlock-style scenario
- one explicit comparison involving a row-versioning option where the environment allows it

Document the expected outcome, the observed outcome, and why it happened.

### 6. Weekly review — 0.5 h

Explain which isolation trade-off is appropriate for a chosen business operation.

### Week 3 outcome

The learner can reason about data correctness under concurrency instead of treating transactions as a simple BEGIN/COMMIT wrapper.

---

# Week 4 — Data Modeling: OLTP to Analytics

**Time budget: 8 hours**

## Focus

Learn to design data structures for their workload rather than using one schema for every purpose.

### 1. Constraints and relational integrity — 1.0 h

- primary keys
- foreign keys
- UNIQUE
- CHECK
- NOT NULL
- defaults
- database-enforced vs application-enforced rules

### 2. Normalization and deliberate denormalization — 1.0 h

- 1NF / 2NF / 3NF at a practical level
- functional dependencies
- update anomalies
- when denormalization can be justified

### 3. OLTP modeling — 1.5 h

- entities and relationships
- keys
- transactional consistency
- common modeling trade-offs
- designing for write-oriented operational workloads

### 4. Dimensional modeling — 2.0 h

- business process
- grain
- fact tables
- dimension tables
- measures
- surrogate keys
- star schema
- operational model vs analytical model

### 5. Slowly Changing Dimensions — 1.0 h

- Type 1
- Type 2
- Type 3 conceptually
- choosing a history strategy

### 6. Cumulative final review & presentation — 1.0 h

The final review does **not** require creating the whole module assignment from scratch.

Artifacts are accumulated throughout Weeks 1–4. The final hour is used to assemble and present evidence such as:

- normalized OLTP schema
- non-trivial queries from Week 1
- indexing/tuning evidence and execution-plan analysis from Week 2
- concurrency evidence from Week 3
- derived star schema
- one SCD decision
- concise explanation of the main trade-offs

### 7. Definition-of-Done check — 0.5 h

Review the accumulated artifacts against the module criteria and identify any gap that still needs remediation.

### Week 4 outcome

The learner can explain why an operational schema and an analytical schema for the same business domain should often look different and can connect the four weeks of work into one coherent engineering story.

---

# Practice Principles

- Prefer reproducible SQL scripts over screenshots.
- Every optimization claim should be supported by an execution plan, measurements, or both.
- Every schema decision should have a stated reason.
- Exercises should use realistic relational data rather than isolated one-table examples.
- Build artifacts cumulatively; do not postpone the entire module deliverable to the final hour.
- AI may suggest solutions, but the learner must validate and be able to explain the accepted result.
- Notes should capture conclusions and engineering reasoning, not copy textbook material.

---

# Definition of Done

Module 01 is complete when the learner can independently:

- solve a complex query using appropriate JOIN, CTE, aggregation and window-function patterns
- read an actual SQL Server execution plan and explain the main operators
- connect important estimated/actual row differences to statistics/cardinality concepts
- explain why SQL Server chooses a scan or seek in a concrete example
- design and justify clustered/nonclustered indexes for a workload
- recognize common non-SARGable patterns
- explain transaction boundaries and the main isolation-level trade-offs
- distinguish locking-based reads from SQL Server row-versioning options at a practical level
- reproduce and explain blocking and common concurrency anomalies
- explain how a deadlock can arise and how to reduce its probability
- design a normalized OLTP schema with database constraints
- define the grain of an analytical fact table
- design a star schema with facts and dimensions
- choose an appropriate SCD strategy for a concrete requirement
- present the cumulative module artifacts without relying on generated explanations

## Tracking

The README defines the learning path; GitHub Issues define concrete work and completion criteria.

**Milestone:** [M01 — Advanced SQL & Data Modeling](https://github.com/roman-vainer/backend-data-engineering-roadmap/milestone/1)

Suggested issue sequence by week:

- **Week 1:** [#1 Setup](https://github.com/roman-vainer/backend-data-engineering-roadmap/issues/1), [#2 JOINs](https://github.com/roman-vainer/backend-data-engineering-roadmap/issues/2), [#3 Aggregation](https://github.com/roman-vainer/backend-data-engineering-roadmap/issues/3), [#4 CTEs](https://github.com/roman-vainer/backend-data-engineering-roadmap/issues/4), [#5 Window functions](https://github.com/roman-vainer/backend-data-engineering-roadmap/issues/5)
- **Week 2:** [#6 Indexes](https://github.com/roman-vainer/backend-data-engineering-roadmap/issues/6), [#7 Execution plans](https://github.com/roman-vainer/backend-data-engineering-roadmap/issues/7), [#8 Statistics/cardinality/SARGability](https://github.com/roman-vainer/backend-data-engineering-roadmap/issues/8)
- **Week 3:** [#9 Transactions](https://github.com/roman-vainer/backend-data-engineering-roadmap/issues/9), [#10 Isolation](https://github.com/roman-vainer/backend-data-engineering-roadmap/issues/10), [#11 Locking/deadlocks](https://github.com/roman-vainer/backend-data-engineering-roadmap/issues/11)
- **Week 4:** [#12 OLTP modeling](https://github.com/roman-vainer/backend-data-engineering-roadmap/issues/12), [#13 Dimensional modeling/SCD](https://github.com/roman-vainer/backend-data-engineering-roadmap/issues/13), [#14 Cumulative module review](https://github.com/roman-vainer/backend-data-engineering-roadmap/issues/14)
