# Module 03 — ETL/ELT & Production Data Pipelines

**Weeks:** 8–11  
**Time:** 32 hours

## Learning Goals

Build reproducible pipelines that behave like production software rather than one-off scripts.

## Topics

ETL/ELT, batch processing, full/incremental loads, CDC concepts, API/SQL Server/file sources, idempotency, retries, checkpoints, watermarks, replay/backfill behavior, schema evolution, data contracts, validation, duplicate handling, scheduling, testing, observability, logging, metrics, and recovery.

## Reference Flow

**Source → Extract → Transform → Validate → Load → Observe**

## Required Practical Path

Build one cohesive batch pipeline connected to the project’s operational/backend data boundary.

It must demonstrate:

- an explicit watermark/checkpoint strategy
- safe re-runs / idempotency
- duplicate handling
- validation
- replay/backfill behavior
- a controlled partial failure
- recovery from that failure
- enough logs/metrics to diagnose what happened

The module does not require adding a new CDC or orchestration product solely for technology coverage.

## Backend + Data Integration

This is one of the first explicit integration points: the backend/SQL Server side is treated as an operational source, and the pipeline must respect that boundary rather than querying an unrelated tutorial dataset.

## Definition of Done

The module is complete when the learner can build a testable pipeline that can be re-run safely, loads data incrementally using a clear change boundary, detects invalid input, handles partial failures, supports replay/recovery, avoids unintended duplicates, and exposes enough information to diagnose failures.

## Planning

The detailed weekly plan and Issues are created shortly before this module begins.
