# Issue 006: Implement Defective Pricing Signal Family

Labels: `mvp`, `signals`, `analytics`, `priority:high`

Parent Epic: #1

## User Story

As an analyst, I need signals that identify contracts where pricing patterns may warrant defective-pricing diligence.

## Scope

Implement explainable rules and baselines for sole-source, low-competition, high-modification, and outlier-pricing patterns in aerospace contracts.

## Acceptance Criteria

- Signal uses competition, award type, obligation, modification, PSC, NAICS, agency, and description features.
- Comparable-award baseline is documented and inspectable.
- Each scored lead includes the reason for the score and source fields used.
- Alternative explanations are generated, including scope change, inflation, urgent need, engineering change, and sustainment complexity.
- Known defective-pricing enforcement examples are included in backtesting.

## Dependencies

- Issue 001.
- Issue 002.
- Issue 004.
- Issue 005.

## Notes

This signal must not imply overpricing by itself. It should identify matters that deserve pricing-data diligence.
