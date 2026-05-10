# Feasibility Study: Aerospace Fraud Signal MVP

Date: May 10, 2026

## Executive Summary

An MVP focused on aerospace-sector fraud detection is feasible if it is narrowly scoped to federal aerospace procurement and grant activity, not the full commercial aerospace market. The strongest wedge is a "FOCUS-ready" analytics product for False Claims Act (FCA) relator counsel, forensic investigators, and specialized data miners that need public-data signals strong enough to justify deeper legal and factual diligence.

The source PDF in this repository, `docs/1777565042260.pdf`, materially changes the opportunity. DOJ's FOCUS initiative says it will prioritize data miners that can explain why their signals correlate to fraud, validate their methods, understand program rules, address alternative explanations, and produce legally sufficient allegations. That favors a product that does not merely rank suspicious contractors. It must produce evidence packages that connect an anomaly to a contract requirement, a claim for payment, a likely falsity theory, and corroborating public records.

Recommendation: proceed with a 12-week MVP, but constrain it to three aerospace fraud theories with public-data support:

1. Defective pricing and undisclosed cost or pricing data on sole-source or low-competition defense aerospace contracts.
2. Nonconforming parts, testing, inspection, and quality certification risk in aircraft, missile, launch, satellite, and avionics supply chains.
3. Cybersecurity false-certification risk for aerospace and defense contractors handling controlled defense information.

## Product Thesis

The MVP should be an aerospace-specific FCA lead intelligence platform. It ingests public procurement, entity, exclusion, enforcement, and corporate data; resolves companies and contract vehicles; applies fraud-theory-specific analytics; and generates a reviewer-ready diligence packet.

The product should not claim to prove fraud. Its job is to identify high-quality leads, reduce analyst time, and package the reasoning needed for counsel or investigators to decide whether to pursue interviews, FOIA, expert review, or a qui tam filing.

## Why Aerospace

Aerospace is a strong vertical for this product because it combines large federal spend, complex contracting, mission-critical quality requirements, concentrated prime-subcontractor networks, and recurring FCA fact patterns.

Current public signals support the market:

- DOJ announced FCA settlements and judgments exceeding $6.8 billion in FY2025, with 1,297 qui tam suits, the highest number reported for a single year.
- DOJ's FOCUS initiative specifically invites sophisticated data miners and prioritizes analytical rigor, regulatory familiarity, and legally sufficient allegations.
- GAO reported that DOD plans to invest nearly $2.4 trillion in its costliest weapon programs, while acquisition costs continue to rise and delivery delays persist.
- GAO reported that NASA planned about $74 billion in FY2025 major-project life-cycle costs, with cost overruns and schedule delays in major projects.
- Recent aerospace and defense FCA matters include defective F-35 pricing, improper markups on Navy aircraft spare parts, nonconforming aircraft parts, and cybersecurity misrepresentation.

These facts suggest a large enough data surface and enforcement history to support a specialized MVP.

## Target Customer

Primary buyer: FCA relator counsel, plaintiff-side firms, forensic accounting firms, investigative research firms, and data-mining relators pursuing aerospace and defense procurement cases.

Secondary buyer: compliance and internal audit teams at aerospace contractors that want to detect exposure before a relator or agency does. This should be a later product line because selling both plaintiff-side lead generation and defense-side compliance can create conflict, trust, and data-use concerns.

Initial ideal customer profile:

- Handles FCA, procurement fraud, defense contracting, or cybersecurity false-claim matters.
- Has legal capacity to evaluate Rule 9(b), scienter, materiality, and falsity.
- Lacks scalable public-data engineering and aerospace-specific analytics.
- Values explainable findings over black-box anomaly scores.

## MVP Scope

The MVP should produce a ranked list of aerospace fraud leads and a diligence packet for each lead.

Included:

- Public awards and transactions from USAspending and FPDS/SAM.gov.
- Entity identity resolution using UEI, CAGE, recipient names, parent relationships, addresses, NAICS, PSC, and known aliases.
- SAM.gov entity and exclusion checks.
- DOJ FCA settlement corpus for labeled examples and typology extraction.
- Contract pattern analytics for aerospace-relevant agencies, offices, NAICS, PSC, and major programs.
- Evidence packet generation with contract IDs, award history, modification timeline, entity network, comparable pricing context, relevant requirement hypothesis, alternative explanations, and recommended next diligence steps.

Excluded from MVP:

- Automated legal complaint drafting.
- Claims that a contractor committed fraud.
- Non-public government data.
- Classified, export-controlled, or controlled unclassified information.
- Broad commercial aviation maintenance and airline operations.
- Full subcontractor visibility where no public records exist.

## Core Data Sources

Minimum data sources:

- USAspending API for federal awards, subawards, transactions, recipients, agencies, NAICS, PSC, obligations, and award descriptions.
- SAM.gov Entity Management API for public entity registration fields and hierarchy indicators.
- SAM.gov Exclusions API for debarment, suspension, ineligibility, and prohibition/restriction checks.
- FPDS contract data, either directly or via USAspending where sufficient.
- DOJ press releases and settlement announcements for supervised typology labels.
- GAO major acquisition reports for program context and risk framing.
- SEC filings and press releases for public contractor disclosures, acquisitions, restatements, and supply-chain claims.

Nice-to-have after MVP:

- Court docket metadata.
- Inspector General reports.
- NASA procurement reports and project assessments.
- FAA enforcement records where relevant.
- Import/export and trade-risk data for parts-origin theories.
- Patent, certification, and standards databases.

## Fraud Signal Candidates

### 1. Defective Pricing and Cost Data

Hypothesis: contractors or subcontractors may have failed to disclose accurate, complete, and current cost or pricing data in negotiated aerospace contracts.

MVP signals:

- Sole-source or low-competition awards with large obligations.
- Repeated upward modifications near production or sustainment phases.
- Outlier pricing compared with peer awards for similar PSC, NAICS, platform, agency, and period.
- Supplier or affiliate relationships suggesting undisclosed lower-cost inputs.
- Award descriptions linked to aircraft, missiles, avionics, satellites, launch systems, or sustainment.

Evidence packet:

- Award and modification timeline.
- Comparable awards.
- Competition and pricing indicators.
- Known related entities.
- Public enforcement analogs.
- Alternative explanations such as inflation, scope changes, urgent operational need, or engineering change orders.

### 2. Nonconforming Parts and Certification Risk

Hypothesis: aerospace suppliers may have billed for parts, tests, inspections, or certifications that did not meet contract specifications.

MVP signals:

- Suppliers tied to critical aircraft, missile, spacecraft, avionics, propulsion, or safety components.
- Repeated small awards across many platforms where quality escapes could scale.
- Brokers, resellers, or non-OEM sourcing indicators in public records.
- Prior exclusions, adverse responsibility data, or enforcement history.
- Sudden award growth by small suppliers in high-criticality PSC categories.

Evidence packet:

- Supplier identity and program exposure.
- Contract requirement hypothesis.
- Public quality or enforcement history.
- Customer agency and platform mapping.
- Alternative explanations such as approved alternate parts, government-directed sourcing, or benign distributor relationships.

### 3. Cybersecurity False Certification

Hypothesis: aerospace and defense contractors may have represented compliance with cybersecurity obligations while failing to implement required controls.

MVP signals:

- Contracts with likely DFARS/NIST 800-171/CUI exposure based on agency, PSC, description, and program type.
- Public disclosures of cyber incidents, weak controls, foreign development relationships, or data handling issues.
- Contractor growth in CUI-heavy work without visible compliance maturity indicators.
- Prior civil cyber-fraud enforcement analogs.

Evidence packet:

- Contract exposure map.
- Public cyber and compliance statements.
- CUI likelihood rationale.
- Known enforcement analogs.
- Alternative explanations such as remedial self-disclosure, inherited systems, or contracts without covered information.

## Technical Feasibility

Technically feasible with a small team. The hardest work is not ingestion. It is entity resolution, explainability, and reducing false positives.

Recommended MVP architecture:

- Batch ingestion jobs for USAspending, SAM.gov, DOJ, GAO, and SEC public data.
- Normalized warehouse with `award`, `transaction`, `recipient`, `entity`, `parent`, `agency`, `psc`, `naics`, `program`, `enforcement_case`, and `signal` tables.
- Entity resolution pipeline combining deterministic identifiers and fuzzy matching.
- Rule-based signal engine first, with model-assisted summarization only after source evidence is linked.
- Analyst UI with lead queue, signal drill-down, source documents, alternative-explanation checklist, and exportable diligence packet.
- Evaluation harness using known DOJ aerospace/defense FCA matters as positive examples and comparable non-enforcement contractors as controls.

Avoid a pure LLM product. LLMs are useful for summarizing award descriptions, extracting typologies from enforcement text, and drafting analyst notes. The product value must come from structured records, traceable calculations, and reproducible reasoning.

## Legal and Compliance Feasibility

Feasible, but the product must be designed as investigative analytics, not legal advice.

Key controls:

- Every lead must be labeled as an allegation-risk hypothesis, not a fraud finding.
- The system must preserve source citations and computation provenance.
- The workflow must force review of alternative explanations.
- Legal theory templates must be reviewed by FCA counsel before use.
- Complaint drafting should remain outside MVP scope.
- The company should maintain a documented methodology for DOJ FOCUS discussions.
- Data acquisition must avoid scraping or retaining restricted, controlled, classified, export-controlled, or improperly obtained information.

The PDF's Rule 9(b) and diligence emphasis makes this more important than normal B2B analytics. A shallow anomaly dashboard would likely create too much noise and too much legal risk.

## Market Feasibility

The market is real but specialized. The MVP should be sold as a high-value expert tool rather than a broad SaaS dashboard.

Likely willingness to pay:

- Plaintiff-side or relator counsel: project-based subscriptions or per-matter diligence packages.
- Forensic/investigative firms: annual seat plus data-volume pricing.
- Compliance teams: later enterprise contracts, after conflict strategy is resolved.

Suggested MVP pricing tests:

- $5,000 to $15,000 per aerospace target dossier.
- $3,000 to $8,000 per month for a limited lead queue and analyst workflow.
- Success-based economics should be evaluated carefully with counsel because legal, ethical, and state bar rules can be sensitive.

Market risk: the buyer universe is smaller than general compliance software, and sales will be relationship-driven. This is acceptable for MVP because a handful of expert users can validate signal quality.

## Competitive Position

Likely competitors include:

- Generic federal-spending search tools.
- Investigative research firms.
- FCA data miners using proprietary workflows.
- Compliance platforms focused on SAM exclusions, supplier risk, or cyber compliance.
- Large legal analytics vendors.

Differentiation should be:

- Aerospace-specific fraud typologies.
- Contract-requirement-aware signals.
- FOCUS-ready methodology documentation.
- Evidence packets that address falsity, materiality, scienter indicators, and alternative explanations.
- Known-case backtesting against aerospace and defense FCA matters.

## MVP Build Plan

### Phase 1: Foundation, Weeks 1-3

- Define aerospace scope using agencies, NAICS, PSC, and keyword dictionaries.
- Ingest USAspending awards and transactions.
- Ingest SAM.gov entity and exclusion data.
- Build entity normalization and duplicate handling.
- Create initial DOJ enforcement case taxonomy.

Exit criteria:

- At least five years of aerospace-relevant federal awards loaded.
- Top contractors and suppliers resolve consistently across identifiers.
- Known enforcement examples can be linked to relevant entities and typologies.

### Phase 2: Signal Engine, Weeks 4-7

- Implement first three signal families.
- Build comparable-award baselines.
- Add modification and obligation timeline features.
- Add alternative-explanation checklist.
- Add signal provenance and confidence scoring.

Exit criteria:

- Known aerospace/defense FCA examples surface in backtests.
- Analysts can explain why each score exists.
- False positives are categorized rather than ignored.

### Phase 3: Analyst Workflow, Weeks 8-10

- Build lead queue and case detail view.
- Generate diligence packets in markdown/PDF.
- Add reviewer notes, disposition, and export.
- Add source-link audit trail.

Exit criteria:

- A user can move from ranked lead to evidence packet in under 30 minutes.
- Each packet includes source links, assumptions, alternative explanations, and next diligence steps.

### Phase 4: Pilot, Weeks 11-12

- Run 2-3 expert pilots with counsel or investigators.
- Score leads for novelty, legal relevance, explainability, and actionability.
- Decide whether to continue, narrow, or pivot.

Exit criteria:

- At least 10 leads reviewed by domain experts.
- At least 2 leads rated strong enough for deeper diligence.
- At least 1 customer willing to pay for continued access or a dossier.

## Team and Budget

Lean MVP team:

- 1 data engineer.
- 1 full-stack engineer.
- 1 data scientist or analytics engineer.
- 1 aerospace/procurement subject matter expert, fractional.
- 1 FCA/procurement counsel, fractional.
- 1 product lead or analyst.

Estimated 12-week cost:

- Low: $120,000 to $180,000 using founders plus fractional experts.
- Moderate: $250,000 to $400,000 with contracted engineering and legal review.
- High: $500,000+ if commercial data licensing, docket data, and enterprise security are included immediately.

## Key Risks

- False positives: public data may show anomalies without proving falsity or scienter.
- Data gaps: subcontractor, invoice, inspection, and internal compliance facts are often non-public.
- Legal risk: careless outputs could look defamatory or like unauthorized legal conclusions.
- Methodology risk: DOJ's FOCUS posture rewards rigor and may deprioritize weak data-miner submissions.
- Sales risk: the best buyers are specialized and may already have internal methods.
- Conflict risk: plaintiff-side and defense-side use cases should not be mixed without a clear business model.

## Success Metrics

Product metrics:

- Percentage of leads with complete source provenance.
- Time from lead discovery to diligence packet.
- Expert actionability rating.
- Known-case recall in backtests.
- False-positive reason distribution.

Business metrics:

- Paid pilot conversion.
- Dossier reorder rate.
- Average revenue per investigation.
- Number of expert-reviewed leads becoming deeper diligence projects.

Quality metrics:

- Every high-priority lead has a specific contract requirement hypothesis.
- Every high-priority lead includes alternative explanations.
- Every model-generated statement is traceable to public records.
- No lead uses restricted or non-public data.

## Go/No-Go Decision

Go if:

- Known aerospace/defense FCA examples can be rediscovered from public data with explainable signals.
- Expert reviewers rate at least 20% of top-ranked MVP leads as worth deeper diligence.
- At least one pilot customer pays for a dossier or subscription.
- Counsel confirms the diligence packet format supports legal review without overclaiming.

No-go or pivot if:

- Signals are mostly generic spend anomalies.
- Entity resolution is too noisy to support source-grade evidence packets.
- Public data cannot establish enough contract-requirement context.
- Buyers only want bespoke research and not repeatable software.

## Bottom Line

The MVP is feasible, but only as a focused aerospace procurement-fraud intelligence product with strong methodology, explainability, and legal review. The opportunity is not a generic "AI fraud detector." It is a disciplined evidence assembly system that helps expert users find, validate, and present aerospace FCA leads in the way DOJ's FOCUS initiative says it will prioritize.

## Sources

- Local source PDF: `docs/1777565042260.pdf`, "FOCUS Initiative for Data Miners Filing Qui Tam Complaints."
- DOJ, "Civil Division Announces FOCUS Initiative for Data Miners Filing Qui Tam Complaints," April 30, 2026: https://www.justice.gov/opa/pr/civil-division-announces-focus-initiative-data-miners-filing-qui-tam-complaints
- DOJ, "False Claims Act Settlements and Judgments Exceed $6.8B in Fiscal Year 2025," January 16, 2026: https://www.justice.gov/opa/pr/false-claims-act-settlements-and-judgments-exceed-68b-fiscal-year-2025
- GAO, "Weapon Systems Annual Assessment: DOD Leaders Should Ensure That Newer Programs Are Structured for Speed and Innovation," June 11, 2025: https://www.gao.gov/products/gao-25-107569
- GAO, "NASA: Assessments of Major Projects," July 1, 2025: https://www.gao.gov/products/gao-25-107591
- USAspending API documentation: https://api.usaspending.gov/
- SAM.gov Entity Management API: https://open.gsa.gov/api/entity-api/
- SAM.gov Exclusions API: https://open.gsa.gov/api/exclusions-api/
- DOJ, Lockheed Martin defective-pricing FCA settlement, February 6, 2025: https://www.justice.gov/opa/pr/lockheed-martin-corporation-agrees-settle-false-claims-act-allegations-defective-pricing
- DOJ, Sikorsky and Derco aircraft spare-parts markup FCA settlement, June 21, 2024: https://www.justice.gov/archives/opa/pr/sikorsky-support-services-inc-and-derco-aerospace-inc-agree-pay-70m-settle-false-claims-act
- DOJ, Teledyne nonconforming aircraft-parts FCA settlement, January 5, 2026: https://www.justice.gov/opa/pr/teledyne-electronic-safety-products-agrees-pay-15m-resolve-false-claims-act-allegations
- DOJ, Aerojet Rocketdyne cybersecurity FCA settlement, July 8, 2022: https://www.justice.gov/archives/opa/pr/aerojet-rocketdyne-agrees-pay-9-million-resolve-false-claims-act-allegations-cybersecurity
- DOJ, Aero Turbine cybersecurity FCA settlement, July 31, 2025: https://www.justice.gov/opa/pr/california-defense-contractor-and-private-equity-firm-agree-pay-175m-resolve-false-claims
