# A1 Methodology — Vendor Tiering and Risk Rating

Adapted from NIST SP 800-30 Rev. 1 (*Guide for Conducting Risk Assessments*), Appendices G–I, simplified to a 5×5 scale. The same method is reused in A2 so that ratings are comparable across artifacts.

## 1. Vendor tiering
A vendor takes the **highest** tier any criterion puts it in.

| Criterion | Tier 1 — Critical | Tier 2 — High | Tier 3 — Moderate |
|---|---|---|---|
| Data sensitivity | Stores or processes customer NPI or authentication data | Accesses internal confidential data | Public or low-sensitivity data only |
| Customer impact | An outage or breach directly affects customers | Affects internal operations | Minimal business impact |
| Substitutability | No ready replacement within 30 days | Replaceable within 30–90 days with effort | Easily replaced |
| System access | Connects to core banking or customer-facing systems | Connects to internal systems | No connectivity |

**Reassessment frequency:** Tier 1 annually · Tier 2 every 2 years · Tier 3 every 3 years or at contract renewal.

## 2. Likelihood scale
| Score | Level | Definition |
|---|---|---|
| 5 | Very high | The weakness is known and exploitable, and events like this occur regularly across the industry. |
| 4 | High | A control is missing or unverified, and the threat is common for this type of service. |
| 3 | Moderate | A control exists but has gaps or limited evidence; exploitation needs moderate effort. |
| 2 | Low | Controls are in place and evidenced; exploitation would need significant effort. |
| 1 | Very low | Strong, independently verified controls; exploitation is highly unlikely. |

## 3. Impact scale
| Score | Level | Definition |
|---|---|---|
| 5 | Severe | Large-scale customer NPI exposure, regulatory enforcement likely, or critical service unavailable for more than 24 hours. |
| 4 | Major | Customer NPI exposure affecting a limited group, required regulatory notification, or significant customer harm. |
| 3 | Moderate | Internal confidential data exposed, or noticeable disruption to a business unit. |
| 2 | Minor | Limited internal impact, handled within normal operations. |
| 1 | Negligible | No meaningful effect on customers, data or operations. |

## 4. Rating matrix
**Rating = Likelihood × Impact**

| Score | Rating |
|---|---|
| 20–25 | 🔴 Critical |
| 10–16 | 🟠 High |
| 5–9 | 🟡 Moderate |
| 1–4 | 🟢 Low |

Findings marked **Unable to verify** are rated as if the control is absent (Likelihood ≥ 4) until evidence is provided. Absence of evidence is not evidence of a control.

## 5. Inherent vs residual risk
- **Inherent risk:** the rating before considering the vendor's controls, based on the tier and the data involved.
- **Residual risk:** the rating after considering only the controls that were **verified** with evidence.

## 6. Remediation targets and recommendation rules
| Rating | Remediation target | Effect on recommendation |
|---|---|---|
| Critical | 30 days, before go-live | Any open Critical finding means **Reject**, or **Mitigate** only with CISO-approved conditions |
| High | 60 days | Open High findings mean **Mitigate**, with conditions and owners |
| Moderate | 90 days | Can be **Accepted** with a tracked remediation plan |
| Low | Next review | **Accept** |

Accepting residual risk requires a named business owner at VP level or above, per the exception process in A3 (planned).

## 7. Worked example
> ✍️ **To do (A1-05):** rate one real finding here, step by step: name the finding, pick the Likelihood level (quote its definition), pick the Impact level (quote its definition), multiply, and state the rating.
