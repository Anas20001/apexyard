# CDR — Centralized Data Repository

**Status**: Active (P0)

## What is CDR?

Medallion-architecture data lakehouse for Remofirst. Ingests CRM, communication, and finance data from HubSpot, Front.com, and Airtable into a Bronze layer of append-only Parquet on AWS S3, with Silver/Gold layers planned on Apache Iceberg.

**Data flow**: HubSpot CRM + Front.com + Airtable → Bronze (S3 Parquet, append-only) → Silver/Gold (S3 Tables / Iceberg)

## Key Technologies

- **Python**: FastAPI, DLT, Polars, DuckDB
- **Data**: Parquet (Bronze), S3 (storage), DuckLake (catalog)
- **Frontend**: TypeScript, Hono, React, Playwright e2e
- **CI/CD**: GitLab CI (lint, validate, deploy, pipeline, pages)
- **Infrastructure**: AWS LightSail, S3, AppFlow

## Active Pipelines

| Pipeline | Source | Destination | Status |
|----------|--------|-------------|--------|
| HubSpot | REST API (cursor-based incremental) | S3 Parquet | ✓ Active |
| Front.com | Zip exports from S3 landing zone | S3 Parquet | ✓ Active |
| Airtable | S3 JSON snapshots | S3 Parquet | ✓ Active |
| Core | Internal S3 | S3 Parquet | ✓ Active |

## Repository

- **GitHub-style**: `remofirst/centralized-data-repository` (but hosted on GitLab)
- **Workspace**: `workspace/cdr` (symlink to live checkout)
- **Docs**: Full technical docs in CDR repo at `docs/`

## Roles

- **Tech Lead**: Anas Mesil — overall system design, bottleneck resolution
- **Data Engineer**: Drives Bronze ingestion, pipeline orchestration
- **Platform Engineer**: Infrastructure, CI/CD, observability

## Key Contacts

- **Tech Lead**: Anas Mesil <anas@remofirst.com>

---

See the CDR repo for full architecture, implementation, and operational details.
