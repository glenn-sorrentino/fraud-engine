# Issue 002: Build Public Procurement Data Ingestion

Labels: `mvp`, `data-ingestion`, `priority:high`

Parent Epic: #1

## User Story

As an analyst, I need federal award and transaction data loaded into a normalized store so that signal calculations can be reproduced and audited.

## Scope

Ingest public award and transaction data from USAspending for the aerospace scope defined in Issue 001.

## Acceptance Criteria

- Ingestion supports configurable fiscal-year range.
- Ingestion stores awards, transactions, agencies, recipients, PSC, NAICS, obligations, award descriptions, competition fields, and modification dates where available.
- Raw source payloads or source retrieval metadata are preserved for auditability.
- Ingestion can be rerun without duplicating records.
- Basic data quality report includes row counts, missing identifiers, duplicate candidates, and top agencies/recipients.

## Dependencies

- Issue 001.

## Notes

Prefer structured APIs over scraping. The MVP does not need every field, but it must preserve enough provenance to defend calculations.
