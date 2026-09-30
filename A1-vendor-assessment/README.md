# A1 — Vendor Security Assessment: Zoom Workplace

> **Status: v0.9 — draft memo, under review.**
> Independent practice assessment based only on publicly available information as of 2026-09-30. Not affiliated with or endorsed by Zoom Video Communications, Inc. *Banco Ejemplo* is a fictional institution.

## Files
| File | Purpose |
|---|---|
| [01-scope.md](01-scope.md) | What is being assessed, for which business use, with what data |
| [02-methodology.md](02-methodology.md) | How vendors are tiered and how every finding is rated (with a worked example) |
| [03-control-review.csv](03-control-review.csv) | 16 control areas mapped to CSA CCM v4 and NIST CSF 2.0, with the evidence behind each answer |
| [04-findings.md](04-findings.md) | 9 rated findings with remediation asks, owners and target dates |
| [05-soc2-triage.md](05-soc2-triage.md) | How I separate a meaningful SOC 2 exception from noise |
| [evidence/](evidence/) | Log of every source reviewed, public or gated |

---

# Assessment Memo

**To:** VP, Consumer Lending — Banco Ejemplo
**From:** Angelo Garcia, Information Security Office (practice)
**Date:** 2026-09-30
**Subject:** Security due diligence — Zoom Workplace for customer video consultations

## Executive summary
Consumer Lending has asked to use Zoom Meetings and Team Chat for video consultations with mortgage applicants, including screen-shared loan documents and cloud recordings. Because the service handles customer nonpublic personal information, it is a **Tier 1 (Critical)** vendor. Zoom's public evidence is strong on the fundamentals: a current ISO 27001:2022 certificate, documented encryption, a public bug bounty and a published subprocessor list. Two things could not be verified from outside a customer relationship: Zoom's SOC 2 Type II report, and the data-retention terms of the third-party AI providers behind AI Companion. The review produced 9 findings, 5 rated High and none Critical. **Recommendation: Mitigate.** Proceed, on the condition that three bank-side settings are locked before go-live and two vendor items are obtained within 60 days.

## Vendor tier and inherent risk
Zoom is **Tier 1** on three of the four tiering criteria in [02-methodology.md](02-methodology.md):
- **Data sensitivity:** recordings and chat will contain income, account numbers and identity documents (customer NPI).
- **Customer impact:** a breach of recorded consultations would directly harm mortgage applicants and trigger notification duties.
- **System access:** none. Zoom does not connect to core banking systems, which lowers but does not remove the tier.
- **Substitutability:** replaceable within 30–90 days (Tier 2 on this criterion).

Inherent risk, before any controls: Likelihood 4 × Impact 4 = **16, High**.

## Key findings
| ID | Finding | Rating |
|---|---|---|
| F-01 | SOC 2 Type II report not obtained (gated); operating effectiveness of Zoom's controls unverified | 🟠 High |
| F-04 | AI Companion sends meeting content to third-party model providers (OpenAI, Anthropic, Perplexity); their retention terms are not public | 🟠 High |
| F-06 / F-07 | Recording retention and SSO/MFA are strong controls, but only if the bank configures them; defaults are open | 🟠 High |

The remaining findings (F-02, F-03, F-05, F-08, F-09) are in [04-findings.md](04-findings.md). Two of them require the business owner to decide: whether to record consultations at all (F-05, since end-to-end encryption and cloud recording cannot be used together) and whether a "without undue delay" breach-notification clause is acceptable (F-03).

## Residual risk and recommendation
**Recommendation: ☑ Mitigate** ☐ Accept ☐ Reject

Rationale:
1. **No Critical findings and a credible assurance baseline.** ISO 27001 certification is current and publicly verifiable, and the control gaps found are evidence gaps or configuration items, not known control failures.
2. **Three of the five High findings are closable by the bank before go-live**, at no cost, through tenant configuration (F-04, F-06, F-07).
3. **The two vendor-dependent items (F-01, F-03) are standard asks** that Zoom fulfils for enterprise customers, and can be closed within the 60-day High-finding window.

Conditions before go-live (owner: Banco Ejemplo IT unless noted):
- Enforce SAML SSO with MFA through the bank's identity provider; disable password login. *(F-07)*
- Lock cloud-recording auto-deletion at 30 days at the account level with deletion notifications on. *(F-06)*
- Disable AI Companion for the Consumer Lending group. *(F-04)*
- Consumer Lending signs a risk acceptance for recording with Zoom-managed keys, or elects E2EE with no recording. *(F-05, owner: business)*

Conditions within 60 days (owner: Vendor Management Office):
- Obtain and review the SOC 2 Type II report and bridge letter; confirm Meetings and Chat are in scope. *(F-01)*
- Negotiate a 24-hour incident-notification clause and written AI-provider retention terms. *(F-03, F-04)*

Expected residual risk once conditions are met: Likelihood 2 × Impact 4 = **8, Moderate**, which is acceptable for a Tier 1 vendor with annual reassessment.

## Next review
**2027-09-30** (Tier 1: annual), or earlier if Zoom changes subprocessors for AI features, the SOC 2 report shows material exceptions, or the business expands the use case beyond consultations.

---

## Resumen ejecutivo (ES)
La unidad de Préstamos al Consumidor solicita usar Zoom Meetings y Team Chat para consultas por video con solicitantes de hipoteca, incluyendo documentos compartidos en pantalla y grabaciones en la nube. Como el servicio maneja información personal no pública de clientes, Zoom se clasifica como proveedor de **Nivel 1 (Crítico)**. La evidencia pública de Zoom es sólida en lo fundamental: certificación ISO 27001:2022 vigente, cifrado documentado, programa público de recompensas por vulnerabilidades y lista publicada de subprocesadores. Dos elementos no pudieron verificarse sin ser cliente: el informe SOC 2 Tipo II y los términos de retención de los proveedores externos de IA detrás de AI Companion. La revisión produjo 9 hallazgos, 5 de severidad Alta y ninguno Crítico. **Recomendación: Mitigar.** Proceder, con la condición de que tres configuraciones del banco se fijen antes de la puesta en marcha y dos documentos del proveedor se obtengan en un plazo de 60 días. Riesgo residual esperado tras cumplir las condiciones: **Moderado**, con reevaluación anual.
