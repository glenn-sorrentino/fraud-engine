# Issue 009: Build Evidence Packet Generator

Labels: `mvp`, `workflow`, `reporting`, `priority:high`

## User Story

As an analyst, I need exportable evidence packets so that leads can be reviewed by counsel or investigators without manually assembling source material.

## Scope

Generate markdown and PDF-ready diligence packets for each high-priority lead.

## Acceptance Criteria

- Packet includes lead summary, fraud-theory hypothesis, scored signals, source citations, award timeline, entity profile, comparable records, and alternative explanations.
- Packet includes "what this does not prove" language.
- Packet includes recommended next diligence steps such as FOIA, expert review, witness development, or contract-document request.
- Packet separates source facts from model-generated summaries.
- Packet can be regenerated reproducibly for the same lead.

## Dependencies

- Issue 006.
- Issue 007.
- Issue 008.

## Notes

This is the MVP's core deliverable. Treat source provenance as a hard requirement.

