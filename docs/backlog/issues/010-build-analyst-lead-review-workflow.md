# Issue 010: Build Analyst Lead Review Workflow

Labels: `mvp`, `frontend`, `workflow`, `priority:medium`

Parent Epic: #1

## User Story

As an analyst, I need a simple workflow to review, disposition, annotate, and export leads.

## Scope

Build a minimal analyst UI or structured notebook workflow for lead review.

## Acceptance Criteria

- User can view ranked leads by signal family, score, agency, entity, platform, and fiscal year.
- User can inspect underlying source records and scoring reasons.
- User can mark leads as `new`, `reviewing`, `deeper-diligence`, `false-positive`, or `discarded`.
- User can record notes and override entity-resolution decisions.
- User can export an evidence packet from the lead detail view.

## Dependencies

- Issue 004.
- Issue 006.
- Issue 007.
- Issue 008.
- Issue 009.

## Notes

For MVP, a simple internal tool is enough. Prioritize review speed and provenance over polish.
