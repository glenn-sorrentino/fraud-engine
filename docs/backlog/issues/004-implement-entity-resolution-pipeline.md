# Issue 004: Implement Entity Resolution Pipeline

Labels: `mvp`, `entity-resolution`, `priority:high`

Parent Epic: #1

## User Story

As an analyst, I need awards, entities, aliases, and parent relationships resolved consistently so that signals are not fragmented across name variations.

## Scope

Implement deterministic and fuzzy matching across UEI, CAGE, recipient name, legal name, address, parent, and aliases.

## Acceptance Criteria

- Deterministic identifiers are matched before fuzzy logic.
- Fuzzy matches include confidence scores and explanation fields.
- Parent-child relationships are stored separately from same-entity matches.
- Analysts can inspect and override uncertain matches.
- Evaluation set includes at least 20 known aerospace contractors and subsidiaries.

## Dependencies

- Issue 002.
- Issue 003.

## Notes

False merges are more dangerous than missed merges. Bias toward review for ambiguous matches.
