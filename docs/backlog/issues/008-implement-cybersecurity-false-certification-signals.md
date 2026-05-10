# Issue 008: Implement Cybersecurity False-Certification Signal Family

Labels: `mvp`, `signals`, `cybersecurity`, `priority:high`

Parent Epic: #1

## User Story

As an analyst, I need signals that identify aerospace contractors whose contracts likely involve cybersecurity obligations and public indicators of potential compliance risk.

## Scope

Implement signals for CUI-heavy contract exposure, defense agency/program work, public cyber incidents, compliance claims, foreign development relationships, and enforcement analogs.

## Acceptance Criteria

- Signal identifies awards likely to involve DFARS, NIST SP 800-171, CUI, or defense information exposure based on public fields.
- Signal captures public cyber/compliance disclosures where available.
- Each lead includes why cybersecurity obligations may apply.
- Alternative explanations include non-CUI contract scope, remedial self-disclosure, inherited systems, and timely remediation.
- Known civil cyber-fraud examples are included in backtesting.

## Dependencies

- Issue 001.
- Issue 002.
- Issue 003.
- Issue 004.
- Issue 005.

## Notes

Be conservative. Public data often indicates exposure, not noncompliance.
