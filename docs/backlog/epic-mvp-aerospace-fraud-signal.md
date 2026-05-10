# Epic: Aerospace Fraud Signal MVP

## Summary

Build a 12-week MVP for an aerospace-focused fraud-signal product that helps expert users identify, validate, and package public-data leads for federal procurement fraud diligence.

The product should support DOJ FOCUS-style rigor: explainable signals, source provenance, program-rule awareness, alternative-explanation review, and legally cautious evidence packets. It should not claim to prove fraud or produce legal filings.

## Problem

DOJ's FOCUS initiative prioritizes data miners who can show analytical rigor, familiarity with program rules, and legally sufficient allegations. Public federal procurement data is available, but it is difficult to transform into high-quality aerospace FCA leads because:

- Entity names, UEIs, CAGE codes, parents, and aliases are hard to resolve consistently.
- Contract transactions and modifications are noisy.
- Generic anomaly scores do not map cleanly to FCA theories.
- Public data rarely proves scienter or falsity on its own.
- Counsel and investigators need source-backed diligence packets, not unexplained rankings.

## MVP Goal

Deliver a working lead intelligence workflow that ingests public aerospace procurement data, applies three fraud-theory-specific signal families, and exports review-ready diligence packets.

## Initial User

FCA relator counsel, forensic investigators, investigative research firms, and specialized data miners evaluating aerospace and defense procurement leads.

## In Scope

- Public procurement data ingestion from USAspending.
- Public entity and exclusion enrichment from SAM.gov.
- Aerospace scope dictionary for agencies, PSC, NAICS, platforms, and keywords.
- Entity resolution across recipient names, UEI, CAGE, addresses, aliases, and parent hints.
- Signal families for:
  - Defective pricing and undisclosed cost or pricing data.
  - Nonconforming parts, testing, inspection, and certification risk.
  - Cybersecurity false-certification risk.
- Evidence packet generation with source citations, alternative explanations, and next diligence steps.
- Backtesting against known aerospace and defense FCA enforcement examples.

## Out of Scope

- Automated complaint drafting.
- Any assertion that a contractor committed fraud.
- Non-public, classified, export-controlled, or controlled information.
- Broad commercial aviation fraud.
- Defense-side compliance productization.
- Paid data licensing unless needed after the MVP pilot.

## Success Criteria

- Known aerospace/defense FCA examples can be rediscovered from public data with explainable signals.
- At least 10 leads are reviewed by domain experts.
- At least 2 leads are rated strong enough for deeper diligence.
- Every high-priority lead includes source provenance and alternative explanations.
- One pilot customer is willing to pay for a dossier or continued access.

## Milestones

1. Data foundation and source ingestion.
2. Aerospace scope and entity resolution.
3. Signal engine for the first three fraud theories.
4. Evidence packet workflow.
5. Backtesting and pilot review.

## Issues

- [Issue 001: Define Aerospace Scope Taxonomy](issues/001-define-aerospace-scope-taxonomy.md)
- [Issue 002: Build Public Procurement Data Ingestion](issues/002-build-public-procurement-data-ingestion.md)
- [Issue 003: Build SAM.gov Entity and Exclusion Enrichment](issues/003-build-sam-entity-exclusion-enrichment.md)
- [Issue 004: Implement Entity Resolution Pipeline](issues/004-implement-entity-resolution-pipeline.md)
- [Issue 005: Create Enforcement Case Taxonomy](issues/005-create-enforcement-case-taxonomy.md)
- [Issue 006: Implement Defective Pricing Signal Family](issues/006-implement-defective-pricing-signals.md)
- [Issue 007: Implement Nonconforming Parts Signal Family](issues/007-implement-nonconforming-parts-signals.md)
- [Issue 008: Implement Cybersecurity False-Certification Signal Family](issues/008-implement-cybersecurity-false-certification-signals.md)
- [Issue 009: Build Evidence Packet Generator](issues/009-build-evidence-packet-generator.md)
- [Issue 010: Build Analyst Lead Review Workflow](issues/010-build-analyst-lead-review-workflow.md)
- [Issue 011: Create Backtesting and Evaluation Harness](issues/011-create-backtesting-evaluation-harness.md)
- [Issue 012: Run Expert Pilot and Go/No-Go Review](issues/012-run-expert-pilot-go-no-go-review.md)

