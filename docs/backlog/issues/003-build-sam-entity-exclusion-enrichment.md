# Issue 003: Build SAM.gov Entity and Exclusion Enrichment

Labels: `mvp`, `data-ingestion`, `entity`, `priority:high`

Parent Epic: #1

## User Story

As an analyst, I need recipient entities enriched with public SAM.gov data so that leads include registration, hierarchy, and exclusion context.

## Scope

Use SAM.gov public entity and exclusion data to enrich recipients from procurement data.

## Acceptance Criteria

- Enrichment supports UEI and name-based lookup where available.
- Entity records capture UEI, legal name, address, registration status, business types, NAICS, PSC, and hierarchy fields available from public data.
- Exclusion checks capture exclusion type, program, agency, dates, and identifiers.
- Missing or ambiguous matches are flagged for analyst review.
- API key and rate-limit handling are documented.

## Dependencies

- Issue 002.

## Notes

Avoid using restricted SAM.gov data. Public-data-only operation is a product requirement.
