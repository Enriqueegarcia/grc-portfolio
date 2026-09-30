# How I Tell a SOC 2 Exception from Noise

Zoom's SOC 2 Type II report is gated (finding F-01), so to show how I read one I used a report a different vendor publishes openly: **Walkover Web Solutions — MSG91 Software Application, SOC 2 Type 2** (https://msg91.com/pdf/soc2.pdf, 52 pages). MSG91 is not being assessed here; this section documents the reading method that will be applied to Zoom's report once obtained.

## Practice report facts
| Fact | Value | Page |
|---|---|---|
| Opinion type | **Unqualified** ("in all material respects… fairly presents… suitably designed… operated effectively") | 7–8 |
| Observation period | **26 Jan 2024 – 26 Apr 2024 (3 months)**; report dated 15 May 2024; cover states next report due 27 Apr 2025 | 1, 8 |
| Trust Services Criteria in scope | **Security, Availability, Confidentiality** (page 6 also mentions Processing Integrity and Privacy, then narrows to the three — the scope statement is internally inconsistent) | 6 |
| Subservice organizations | **Carve-out** method. Listed: AWS, GitHub, MongoDB, MySQL, Google Workspace. Complementary subservice controls are mapped only for AWS. | 6, 31 |
| Tests with exceptions | **0 of 144** test rows; every one reads "No exceptions noted" | 32–52 |
| Auditor | Signed by an individual CPA (license number given), not a named audit firm | 8 |
| CUECs listed | Yes — ~10, mostly access management and secure transmission on the customer side | 30 |

## My five triage criteria
1. **Relevance to my use case.** Is the failed control one my data or process depends on? An exception in a control I don't rely on is noise for *my* assessment (but not for the vendor).
2. **Deviation rate vs sample size.** 1 miss in 25 samples is a slip; 5 in 25 is a broken control. The report must show both numbers.
3. **Management response.** Was the root cause fixed, and by when? A dated remediation with re-test evidence closes the item; "management is aware" does not.
4. **Compensating controls.** Does another *tested* control cover the same risk? If so, the exception drops a level.
5. **Period coverage and staleness.** How long was the period, and does it reach today? Short periods and old dates need a **bridge letter** or the next report before I rely on them.

## Applying the criteria to the practice report
This report has zero exceptions, and that's exactly the kind of result that needs the most scrutiny, because a clean opinion is not the same as low risk.

**Criterion 5 does the most work here.** The observation period is only three months, the minimum most auditors will accept; it says little about how controls behave across a full year of staff changes and releases. Worse, the report is dated May 2024 and its own cover promised the next one by April 2025. As of September 2026 there is no newer report on the vendor's site, so this evidence is **stale by more than a year**. If this were a Tier 1 vendor for the bank, the first ask would be a current report or a bridge letter, and until then the assurance value is close to nil.

**Criterion 4, read in reverse.** The vendor's controls lean on subservice organizations, and the report carves them out: physical security, environmental controls, BC/DR testing and media sanitization are all "expected to be implemented by AWS" (p. 31). Those are the very controls a bank cares about, so the clean opinion covers less than it appears to. I would need AWS's own SOC 2 to close the loop. The subservice list also names MySQL, which is software, not an organization, a drafting error that lowers my confidence in the description's rigor.

**Criterion 2 can't be applied** because the testing matrices state results but not sample sizes. "No exceptions noted" without "of N samples" is a weaker statement than it looks.

**Two things that would be exceptions if they appeared in Zoom's report:** any deviation in CC6 (logical access) or CC7 (change management and monitoring), because the bank's use case depends on recordings being reachable only by the right people. A single missed access review would be relevant, not noise.

**Verdict on this report as evidence:** unqualified opinion, but short period, stale, carved-out infrastructure, no sample sizes, and an individual signer rather than a firm. I would rate its assurance value as **Low** and request the current report before relying on it.

## CUECs a bank would have to operate itself (for Zoom)
SOC 2 reports assume the customer does its part. For the Zoom use case, Banco Ejemplo owns these, and each maps to a finding in [04-findings.md](04-findings.md):
1. Enforce SAML SSO with MFA and disable password login on the Zoom tenant. *(F-07)*
2. Approve, review quarterly, and remove user access to the tenant when staff leave. *(CUEC pattern from the practice report, p. 30)*
3. Configure and lock cloud-recording auto-deletion at 30 days. *(F-06)*
4. Restrict which data may be shared in meetings, and disable AI Companion for the Consumer Lending group. *(F-04)*
5. Read Zoom's subprocessor and security-bulletin notices and re-assess when they change. *(F-02, next-review triggers)*
