# Repository Audit: Backend + Data Engineering Roadmap

**Audit date:** 2026-10-09  
**Scope:** The repository’s main README, roadmap, AI-engineering guide, all seven module READMEs, and the visible Module 01 GitHub issues and milestone. This is an audit only; no roadmap content has been changed.

## 1. Executive assessment

The roadmap has a coherent seven-module data-engineering progression and a well-defined Microsoft platform focus. Its 26-week schedule and module hour totals reconcile to 208 hours, and Module 01 gives learners a stronger SQL Server foundation than a typical tool-first data course. A single flagship project and explicit AI review principles also support the intended engineering orientation.

The main risks are not a broken sequence but **scope and integration ambiguity**. The stated outcome is a Backend Engineer (.NET) with strong Data Engineering skills, while the detailed learning work is almost entirely data-platform work and the ASP.NET API appears only in the final architecture. The roadmap says it builds on a backend foundation, but does not explicitly state that foundation as a prerequisite or show how the existing backend is carried through the earlier modules. Separately, Module 04 and Module 06 pack many substantial topics into four weeks each, and Module 01’s final assignment is allotted one hour despite a broad set of deliverables.

**Overall judgment:** A good framework for a learner who already has backend experience, but it should state that assumption, make the project’s .NET/data integration incremental, narrow a few broad modules, and make the time budget for the AI work and Module 01 synthesis credible. Keep the seven-module structure and Microsoft ecosystem; no wholesale redesign is justified.

## 2. What is already strong

- **Clear target and progression.** The overview names the professional target and the seven-module sequence from SQL through integrated system design ([README.md, lines 3–7 and 21–31](../README.md#L3-L31); [ROADMAP.md, lines 3–11](../ROADMAP.md#L3-L11)).
- **Consistent overall calendar.** The module weeks and hours agree across the main README and the roadmap’s time-budget table: 26 weeks, 208 hours, approximately eight hours per week ([README.md, lines 9–31](../README.md#L9-L31); [ROADMAP.md, lines 379–392](../ROADMAP.md#L379-L392)).
- **Concepts precede platform specialization.** SQL, Python, pipeline reliability, and analytical architecture come before Spark/Databricks and Azure. This gives platform learning useful context rather than making the course a tour of cloud services ([ROADMAP.md, lines 7–11 and module sections](../ROADMAP.md#L7-L11)).
- **A coherent Microsoft center of gravity.** SQL Server and Azure SQL, Azure Storage/ADLS Gen2, ADF, Azure Databricks, and PySpark are consistently named as the core. Fabric is explicitly awareness-only, not a competing core platform ([README.md, lines 14–19](../README.md#L14-L19); [ROADMAP.md, lines 222–253](../ROADMAP.md#L222-L253); [Module 06](../modules/06-azure-data-dataops/README.md)).
- **The flagship project is designed to connect modules.** The project evolves from an operational model through ingestion and analytics to cloud deployment and operations; its domain is intentionally left open ([README.md, lines 35–41](../README.md#L35-L41); [ROADMAP.md, lines 326–345](../ROADMAP.md#L326-L345)).
- **Module 01 has unusually good instructional detail.** Its weekly allocations total eight hours apiece; it includes practice, review, outcomes, evidence-based tuning, and a clear Definition of Done ([Module 01, weeks 1–4](../modules/01-advanced-sql-data-modeling/README.md#L31-L294); [Definition of Done](../modules/01-advanced-sql-data-modeling/README.md#L296-L327)).
- **The Module 01 issues largely operationalize the README.** Issues #1–14 cover setup, the named SQL/modeling topics, and a final practical assignment; issue #1 and issue #14 show the `M01 - Advanced SQL & Data Modeling` milestone. The final issue includes an AI rule that reinforces independent understanding. See [issues #1–14](https://github.com/roman-vainer/backend-data-engineering-roadmap/issues?q=is%3Aissue+is%3Aopen+M01).
- **AI is framed appropriately as an engineering aid.** The AI guide emphasizes understanding, review, validation, testing, and ownership rather than treating generated output as authoritative ([ai-engineering/README.md, lines 3–23](../ai-engineering/README.md#L3-L23)).

## 3. Structural inconsistencies

1. **The repository tree is stale.** `README.md` lists `PROGRESS.md`, but that file is not present in the tracked repository. The same section says milestones and GitHub issues “will be added progressively,” although 14 Module 01 issues and an M01 milestone already exist ([README.md, lines 51–70](../README.md#L51-L70); repository file list).
2. **Module task detail is uneven.** Module 01 has a four-week syllabus, while Modules 02–07 provide topic summaries, outcomes, and the statement that detailed weekly tasks/issues will be added later. The high-level progression is consistent, but learners cannot yet judge the week-by-week workload or practice expectations for most of the program ([Module 01](../modules/01-advanced-sql-data-modeling/README.md); [Modules 02–07](../modules/)).
3. **The division of responsibility is stated but incompletely linked.** Module 01 says its README defines the learning path and its issues define concrete work; the module page does not link to those issues, and no comparable issue-level structure is visible for Modules 02–07. The M01 milestone makes its issue group visible, but the overview’s repository tree and status text do not reflect that current structure ([Module 01, lines 325–327](../modules/01-advanced-sql-data-modeling/README.md#L325-L327); [README.md, lines 51–70](../README.md#L51-L70)).
4. **AI time is claimed, not mapped.** Both overview documents assign approximately 15–20 hours of the 208-hour budget to AI-assisted engineering, but the module plans do not show how that time is distributed. Module 01 identifies a single 0.5-hour AI activity; the standalone AI guide lists scenarios and principles without a schedule ([README.md, lines 43–49](../README.md#L43-L49); [ROADMAP.md, lines 349–375](../ROADMAP.md#L349-L375); [AI guide](../ai-engineering/README.md)).
5. **Repeated summaries create a maintenance risk.** The main README, roadmap, and module READMEs repeat module names, weeks, hours, and focus. This is useful orientation, but a single explicit source of truth—or a lightweight consistency check—would reduce drift. At present, those values do match.

## 4. Learning-sequence problems

- **Make the backend prerequisite explicit and connect it earlier.** The roadmap says Data Engineering is built on a backend foundation, but does not define that foundation. C#/.NET/ASP.NET is named as the primary backend ecosystem, yet implementation appears in Module 07’s target architecture rather than in earlier practice. This is reasonable if the learner already has backend experience; it is not sufficient evidence that the modules themselves build that experience. State the expected .NET/API baseline and carry the learner’s existing backend/data boundary through the project before the final module. Do not turn this into a second beginner backend curriculum.
- **The project’s stated evolution and the module tasks are not fully synchronized.** The flagship-project list includes “backend-accessible transactional data” as step 2, but Modules 01–06 do not specify an API/data-access integration deliverable. The final integration module therefore risks becoming the first real integration rather than the culmination of prior work ([ROADMAP.md, lines 332–345](../ROADMAP.md#L332-L345); [Module 07](../modules/07-integrated-backend-data/README.md)).
- **Clarify the practical environment for Module 05.** Spark concepts precede Azure, which is pedagogically sensible. However, the module also promises Databricks workspace, compute, and jobs practice before the Azure platform module explains deployment and services. State whether this work uses a local Spark environment, an already available Databricks workspace, or conceptual exercises; otherwise access and setup can obscure the Spark learning goals ([ROADMAP.md, lines 177–210](../ROADMAP.md#L177-L210); [Module 05](../modules/05-pyspark-databricks/README.md)).
- **Reduce repeated table-format coverage.** Module 04 introduces Delta Lake, Iceberg, schema evolution, time travel, metadata, catalogs, and interoperability; Module 05 revisits Delta Lake and schema evolution in practice. Keep Delta Lake as the practical format aligned with Databricks, with Iceberg at comparison/awareness level. Place the hands-on Delta work in the Spark/Databricks sequence rather than trying to teach both formats deeply before it ([ROADMAP.md, lines 159–169 and 185–206](../ROADMAP.md#L159-L206); [Module 04](../modules/04-warehouse-lakehouse-analytics/README.md)).
- **Keep dbt’s role bounded and explicit.** “Fundamentals” and tests/documentation/lineage are appropriate exposure, but the roadmap does not identify a target runtime or explain how dbt relates to the Python/ADF/Spark transformations elsewhere. Keep it a focused SQL-based analytics-engineering exercise; avoid making it a second orchestration or transformation platform.
- **Use the planned foundations to specify incremental-load semantics.** Module 03 names CDC concepts, watermarks only implicitly through incremental loads, checkpoints, and recovery, but does not say how learners establish a safe change boundary or ensure source consistency. A concrete, small batch example should exercise the interaction of watermark/checkpoint, idempotency, and recovery; a new CDC product is not needed ([ROADMAP.md, lines 103–123](../ROADMAP.md#L103-L123)).

## 5. Missing topics

Prioritize omissions that make the promised system hard to implement or reason about; do not add a catalog of technologies.

- **Prerequisite statement:** baseline SQL, backend/API experience in .NET, Git/command-line comfort, and general programming familiarity. This keeps the stated eight-hour schedule plausible without assuming a programming beginner.
- **An incremental .NET-to-data integration thread:** make explicit how the existing ASP.NET/SQL Server boundary produces or exposes data for ingestion, and where that boundary is tested. The backend engineering may be assumed, but the integration should be practiced before Module 07.
- **Database and pipeline change management:** briefly specify how schema changes, configuration, and data-contract changes are versioned and promoted between environments. These connect Module 01’s database design to Module 06’s CI/CD and Module 07’s system operation.
- **Observable, correct incremental loads:** identify a concrete watermark/checkpoint and replay/recovery exercise in Module 03. The roadmap already contains the relevant building blocks; the gap is their explicit, end-to-end acceptance criteria.
- **A visible time plan for cross-cutting AI use:** account for the claimed 15–20 hours inside module/week budgets and distinguish planned learning exercises from ordinary tool use.

Module 01’s high-level topic coverage is sound. One worthwhile refinement is to make SQL Server-specific behavior in scope more concrete where it supports the listed outcomes—for example, state whether snapshot isolation means `SNAPSHOT`, `READ_COMMITTED_SNAPSHOT`, or conceptual comparison, and make the practical concurrency exercise verify a chosen outcome. More advanced optimizer/administration topics (such as parameter-sensitive plans or Query Store) should be optional extension work, not new core requirements in the existing 32 hours.

## 6. Topics to remove or reduce

- **Reduce Apache Iceberg to conceptual comparison.** The Microsoft/Databricks target does not justify implementing two table formats in a 208-hour program. Keep an explanation of the trade-offs, but make Delta Lake the hands-on path.
- **Avoid teaching both Pandas and Polars as core skills.** Module 02 has only 24 hours and calls for basics of both. Select one for practice (or keep the second as recognition-only) so learners spend the time on testable Python data-processing patterns ([ROADMAP.md, lines 58–87](../ROADMAP.md#L58-L87)).
- **Keep streaming as awareness rather than a second pipeline specialty.** Module 03 is principally batch; Module 05 calls for only basic streaming concepts. Preserve that scope and avoid adding a streaming platform or implementation requirement.
- **Limit IaC, Docker, and Fabric to their stated purpose.** The roadmap already marks IaC as basic and Fabric as optional; maintain those limits rather than growing Module 06 into a second platform/DevOps curriculum ([ROADMAP.md, lines 249–253](../ROADMAP.md#L249-L253)).
- **Do not expand AI into a parallel specialization.** The existing cross-cutting guide and validation principles are appropriate. Add traceable practice/time allocations, not a separate AI module or a long list of required tools.

## 7. Workload assessment

The **aggregate arithmetic is sound**: 26 weeks × 8 hours = 208 hours, and all seven module allocations sum to 208. Module 01’s four weekly activity budgets also each total eight hours. The uncertainty is the scope within those budgets, not the headline arithmetic.

| Module | Assessment |
|---|---|
| 01 — Advanced SQL & Data Modeling (32 h) | Dense but credible for someone already comfortable with programming and basic SQL. The final assignment’s one-hour slot is not credible for its full deliverables; it should synthesize work already completed in earlier weeks or receive more explicit time. The 0.5-hour environment setup is also fragile if installation or sample-data setup fails. |
| 02 — Python for Data Engineering (24 h) | A reasonable bridge for a non-beginner, but too short for equal hands-on depth in Python structure, testing, APIs, multiple formats, database access, Pandas, and Polars. Narrow the library scope. |
| 03 — ETL/ELT & Production Pipelines (32 h) | Plausible if kept to one small, batch-oriented pipeline. The reliability concepts are numerous; define one cohesive practice deliverable rather than implying production mastery of each individually. |
| 04 — Warehouse/Lakehouse & Analytics Engineering (32 h) | Most obviously overloaded: dimensional modeling, warehouse/lake/lakehouse distinctions, medallion layers, storage/partitioning, dbt, quality, two table formats, catalogs, and interoperability. Keep a practical core and downgrade format/catalog breadth to short comparisons. |
| 05 — PySpark & Databricks (32 h) | Plausible for introductory competence if Spark execution, batch transformations, and one Databricks workflow are central. Performance, Delta, streaming, workspace/compute, and production structure together need strict prioritization. |
| 06 — Azure Data Platform & DataOps (32 h) | Broad for four weeks: several Azure services plus CI/CD, Docker, secrets, monitoring, security, cost, deployment, and IaC. Select one end-to-end deployable path; treat the rest as recognition-level concepts. |
| 07 — Integrated Backend + Data Engineering (24 h) | Credible only as a capstone/integration/review of a project built progressively. Not enough time to build the API-to-cloud-to-lakehouse system and all portfolio evidence from scratch. |

The overall workload is **realistic as a guided self-study plan for an experienced backend developer**, provided the later modules have bounded practice deliverables and the project is incrementally implemented. It is not realistic to treat every listed item as independently mastered or to defer integration to the last three weeks.

## 8. Module 01 detailed review

### Plan and topic order

The four-week sequence is generally sound:

1. Advanced queries and relational question-solving.
2. Indexes, plans, statistics, and measured tuning.
3. Transactions, isolation, locking, and concurrency experiments.
4. Constraints, normalized OLTP design, dimensional modeling, SCDs, and synthesis.

The order moves from query fluency to performance and correctness, then model design. It assumes a reusable relational training database exists from the outset, appropriately reflected in issue #1. In Week 2, statistics/cardinality are introduced after execution-plan operators; teach or revisit estimates and statistics alongside plan interpretation so learners can explain estimated-versus-actual behavior before tuning.

### Practice, outcomes, and Definition of Done

Practice is stronger than passive topic coverage: the plan calls for actual execution plans, before/after comparison, two-session experiments, realistic relational data, and justified schema/index choices ([Module 01 practice principles](../modules/01-advanced-sql-data-modeling/README.md#L296-L303)). The Definition of Done is aligned with the stated learning goals and requires independent explanation rather than mere task completion ([Module 01, lines 307–323](../modules/01-advanced-sql-data-modeling/README.md#L307-L323)).

The clearest mismatch is the **one-hour final assignment**. Its README deliverables include an OLTP schema, analytical queries, index choices, a star schema, an SCD decision, and trade-off explanations. GitHub issue #14 further asks for an actual plan analysis, a concurrency experiment, and a self-review. That is a good capstone checklist, but not a one-hour activity if created from scratch. Make clear that the artifacts are accumulated throughout the four weeks and use the final hour for review/presentation—or reallocate the time.

### GitHub issue alignment and granularity

The 14 open M01 issues are sensibly divided into setup (#1), twelve topic-focused tasks (#2–13), and an integrative assignment (#14). Their titles and acceptance criteria closely track the README, and the single M01 milestone provides a usable grouping. This is not obviously excessive fragmentation for a course managed through issues: most topic issues describe one bounded exercise with a Definition of Done.

Two refinements would improve alignment:

- Link the milestone/issues from the Module 01 README and identify the intended week or dependency explicitly; do not rely on issue numbers as the learning sequence.
- Ensure issue #14 is understood as a cumulative review. It asks for more than the README’s one-hour final-assignment slot, while its “one concurrency experiment” is less specific than the README’s requirement to reproduce and explain blocking and concurrency anomalies. The final issue need not repeat all Week 3 exercises, but its acceptance criteria should point to those prior artifacts.

### Advanced SQL Server/data-modeling gaps

No major foundational category is absent for a four-week advanced-SQL module: query patterns, indexing and plans, transaction isolation/concurrency, relational integrity/normalization, and dimensional modeling are all present. The high-value clarifications are SQL Server-specific isolation behavior and the evidence/artifact expected for the final concurrency and tuning work. Topics such as parameter-sensitive plan diagnosis, Query Store, and deeper engine internals are useful extensions, not justified additions to the core time budget.

## 9. Recommended changes ranked

### Critical

1. **State the learner baseline and preserve the target.** Explicitly say whether the learner is expected to already have working .NET/ASP.NET backend experience and basic SQL/programming skills. If yes, frame this accurately as a Data Engineering specialization for a backend engineer, not a beginner path to backend competence.
2. **Make integration incremental and bound the capstone.** Name small backend/data integration evidence before Module 07, and reserve the final module for integration, recovery/system-design reasoning, and portfolio presentation—not first implementation of the entire architecture.
3. **Resolve Module 01’s final-assignment time mismatch.** Treat the one-hour slot as synthesis of artifacts built earlier, or allocate enough of Week 4 for the issue #14 deliverables.

### Important

1. **Reduce Module 04 breadth.** Keep dimensional modeling and a practical lakehouse path central; make Iceberg, catalogs, and interoperability short conceptual comparisons. Use Delta for the hands-on path that continues into Databricks.
2. **Constrain the cloud and Spark modules to one practical path.** Define the Module 05 execution environment and choose a minimal end-to-end Azure deployment for Module 06; label remaining services/operations as awareness rather than equal-depth outcomes.
3. **Make weeks/practice observable in Modules 02–07.** Add a lightweight weekly plan and one demonstrable outcome per module, sufficient to show that the scope fits the eight-hour weeks. Do not necessarily bring every module to Module 01’s level of detail.
4. **Show where cross-cutting AI time comes from.** Map the stated 15–20 hours into existing module/week budgets and keep the established human validation/ownership standard.
5. **Update repository structure and issue guidance.** Remove or add the stale `PROGRESS.md` entry as intended, update the claim that issues/milestones are still to be added, and link Module 01 issues from its README. Use issue descriptions or links—not numbering alone—to communicate sequence.
6. **Specify one safe incremental-load exercise.** Define a batch watermark/checkpoint, replay behavior, and recovery criterion using the current stack, without introducing a new orchestration product.

### Optional

1. In Module 01, interleave statistics/cardinality with execution-plan reading and state the SQL Server snapshot-isolation behavior to be demonstrated.
2. Select one Python dataframe library for required practice; keep the alternative as optional awareness.
3. Keep streaming, Fabric, deeper IaC, and advanced SQL Server internals explicitly outside core completion criteria unless future revisions add time.

## 10. Final proposed roadmap structure

The existing seven modules and their order are justified; retain them. The following refinement is warranted, not a technology-led redesign:

| Sequence | Retained focus | Necessary refinement |
|---|---|---|
| 01 · Weeks 1–4 | Advanced SQL & data modeling | State prerequisites; complete a bounded relational-model/query baseline; treat the final assignment as cumulative. |
| 02 · Weeks 5–7 | Python for Data Engineering | Focus on testable Python data components and one primary dataframe library. |
| 03 · Weeks 8–11 | ETL/ELT & production pipelines | Implement one observable, idempotent batch pipeline with explicit incremental-load and recovery behavior. |
| 04 · Weeks 12–15 | Warehouse/lakehouse & analytics engineering | Prioritize grain, dimensional modeling, layered data, Parquet, and focused dbt fundamentals; keep Iceberg/catalog breadth conceptual. |
| 05 · Weeks 16–19 | PySpark & Databricks | Learn batch Spark execution first, then run one production-shaped workflow in a clearly specified Databricks environment; streaming stays awareness-only. |
| 06 · Weeks 20–23 | Azure data platform & DataOps | Deploy the selected workflow through a minimal Microsoft/Azure path; treat secondary services and advanced operations proportionately. |
| 07 · Weeks 24–26 | Integrated backend + data engineering & system design | Integrate, validate, recover, document, and present the project developed along the way; do not make this the first backend/data integration. |

This structure keeps the professional target, 26-week/208-hour budget, and Microsoft ecosystem intact. It does not select a flagship-project domain.
