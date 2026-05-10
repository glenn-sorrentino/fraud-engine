# Issue 011: Create Backtesting and Evaluation Harness

Labels: `mvp`, `testing`, `analytics`, `priority:high`

Parent Epic: #1

## User Story

As a product team, we need to test whether the signal engine can rediscover known cases and separate useful leads from noise.

## Scope

Create an evaluation harness using known enforcement examples and comparable non-enforcement entities or awards.

## Acceptance Criteria

- Harness measures recall against known enforcement examples.
- Harness records false positives and assigns a reason category.
- Harness compares signal scores before and after rule changes.
- Evaluation output is reproducible and stored as an artifact.
- Results include recommended threshold settings for pilot review.

## Dependencies

- Issue 005.
- Issue 006.
- Issue 007.
- Issue 008.

## Notes

Do not optimize only for known cases. The evaluation should also reveal noisy rules before pilot users see them.
