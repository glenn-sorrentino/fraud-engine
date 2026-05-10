# Issue 007: Implement Nonconforming Parts Signal Family

Labels: `mvp`, `signals`, `analytics`, `priority:high`

## User Story

As an analyst, I need signals that identify aerospace suppliers where parts, testing, inspection, or certification risk deserves deeper review.

## Scope

Implement signals for high-criticality parts suppliers, broker/reseller indicators, rapid award growth, prior adverse records, and platform exposure.

## Acceptance Criteria

- Signal identifies awards tied to aircraft, missile, spacecraft, launch, avionics, propulsion, safety, and testing components.
- Signal captures supplier size, award growth, repeated small awards, program exposure, and entity risk indicators.
- Evidence output distinguishes OEM, authorized reseller, broker, distributor, and unknown roles when public data supports it.
- Alternative explanations include approved alternate sourcing, government-directed sourcing, benign distribution, and administrative award text ambiguity.
- Known nonconforming-parts or falsified-testing enforcement examples are included in backtesting.

## Dependencies

- Issue 001.
- Issue 002.
- Issue 003.
- Issue 004.
- Issue 005.

## Notes

Because many quality facts are non-public, this signal should be framed as a supply-chain diligence trigger.

