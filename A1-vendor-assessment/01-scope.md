# A1 Scope — Zoom Workplace

> ✍️ **DRAFT (task A1-03):** read every section, then rewrite anything that doesn't sound like you. An interviewer may ask you to explain any sentence here. Delete this box when done.

## Purpose
This assessment evaluates whether Zoom Workplace provides adequate security controls for a proposed use at Banco Ejemplo. It supports a single decision: whether Consumer Lending may adopt the service, and under what conditions.

## Business use case
Banco Ejemplo's Consumer Lending unit wants to use Zoom Meetings and Zoom Team Chat for video consultations with mortgage applicants. Loan officers would walk customers through applications, review documents on screen, and answer questions. Some meetings may be recorded to Zoom's cloud for quality assurance.

## Data in scope
- Customer nonpublic personal information (NPI) spoken aloud during meetings: names, income, account and loan details.
- Loan documents shown by screen share: pay stubs, bank statements, tax returns, identity documents.
- Cloud recordings, transcripts and chat messages containing the above.
- Meeting metadata: participant names, email addresses, IP addresses, meeting times.

## In scope / Out of scope
**In scope:** Zoom Meetings, Zoom Team Chat, cloud recording and transcription, AI Companion features available in those products, and Zoom's corporate security program as it supports them.

**Out of scope:** Zoom Phone, Zoom Contact Center, Zoom Rooms hardware, on-premises connectors, and Banco Ejemplo's own endpoint and network security.

## Assessment approach
Desk review of public evidence: the Zoom Trust Center, Zoom's CSA STAR registry entry and CAIQ (Consensus Assessments Initiative Questionnaire), and published security and privacy documentation. Controls are reviewed against 16 control areas mapped to the CSA Cloud Controls Matrix v4 and NIST Cybersecurity Framework 2.0, and rated using [02-methodology.md](02-methodology.md).

**Limitation:** Zoom's SOC 2 Type II report is available only to customers through the Trust Center. It was not obtained. It is recorded as an **information request** that must be fulfilled before approval, not treated as a satisfied control.

## Disclaimer
Independent practice assessment based only on publicly available information as of 2026-09-30. Not affiliated with or endorsed by Zoom Video Communications, Inc. Banco Ejemplo is a fictional institution.
