---
title: Revenue Pulse
tags: [data-engineering, analytics-engineering, reliability]
permalink: /projects/revenue-pulse
---

# Revenue Pulse

## TL;DR

Revenue Pulse is a local-first data engineering project that turns raw synthetic
SaaS billing and product events into reliable weekly revenue KPIs. It is built
to show operational discipline: idempotent reruns, explicit quality gates, and
clear backfill behavior.

## Problem

Revenue reporting breaks when pipelines are hard to rerun, late data arrives,
or data quality checks are treated as optional. The goal here was to build a
small pipeline that handles those failure modes directly.

## Data

- Deterministic synthetic SaaS event data generated for ~30 days.
- Raw files are partitioned by ingest date under `data/raw/...`.
- Two event contracts are enforced: `billing_events` and `product_events`.

## Method

- Stack: Python, DuckDB, dbt-core, pytest, GitHub Actions.
- Bronze: staged raw loads with contract validation.
- Silver: typed and deduplicated clean tables.
- Gold:
  - `gold.fct_mrr_daily` with new/expansion/contraction/churn components.
  - `gold.mart_exec_weekly` with NRR, GRR, ARPA, active accounts, and failed payment rate.
- Reliability choices:
  - 3-day late-arrival reprocessing window.
  - Explicit failure on blank required fields and duplicate `event_id`.
  - Date-range backfill command for controlled replay.

## Results

- Unit tests: `8 passed`.
- Null-required-field drill: pipeline fails at contract validation as expected.
- Duplicate-event drill: pipeline fails at uniqueness gate as expected.
- Idempotency check: rerunning the same date produced unchanged weekly KPI hash.

## Output sample

Recent weekly sample from the generated mart:

| week_start | net_mrr_change_cents | closing_mrr_cents | active_accounts | failed_payment_rate |
| --- | --- | --- | --- | --- |
| `2026-01-26` | `50000` | `50000` | `32` | `0.0464` |

## Links

- [Source repo](https://github.com/elsalmi/revenue-pulse)

## Risks

- This MVP is local-first and batch-only by design.
- It does not include cloud orchestration, CDC, or live streaming in this pass.
- KPI semantics still depend on source event design and assumptions.

## What changed

- Built a complete local DE pipeline from seed data to executive mart.
- Added deterministic quality drills for duplicates and required-field failures.
- Added reproducible daily and backfill run commands.

## What I’d improve next

1. Add lightweight dashboarding over `mart_exec_weekly`.
2. Add data-contract versioning and change alerts.
3. Add cloud deployment path (containerized run + scheduled orchestration).
