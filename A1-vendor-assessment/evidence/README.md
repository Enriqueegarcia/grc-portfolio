# Evidence Log

Every source used in A1, retrieved **2026-09-30** unless noted. Public pages change; re-check dates before the v1.0 release.

Access notes: Zoom's Trust Center (trust.zoom.com) gates most compliance documents behind a corporate-email "magic link". This assessment was performed without customer access, so gated documents are recorded as **information requests** rather than reviewed evidence.

| # | Document | Source URL | Version / date | Access | Used for |
|---|---|---|---|---|---|
| E-01 | Zoom Security page | https://www.zoom.com/en/trust/security/ | live page | public | C08, C09 |
| E-02 | Zoom encryption whitepaper — "Understanding encryption in the Zoom Workplace platform" | https://media.zoom.com/download/assets/zoom-encryption-whitepaper.pdf/bc3e8eb2e9ef11ed991baa083779b9cc | PDF, undated on page | public | C05, C06 |
| E-03 | Zoom Cryptography Whitepaper (E2EE design) | https://github.com/zoom/zoom-e2e-whitepaper | GitHub, versioned | public | C05, C06 |
| E-04 | Zoom Subprocessors list | https://www.zoom.com/en/trust/subprocessors/ | last change 2026-04-29 | public | C14, C15 |
| E-05 | Zoom blog — AI data governance / data residency options | https://www.zoom.com/en/blog/ai-companion-data-residency-options/ | 2025-10-16 | public | C15, C13 |
| E-06 | AI Companion Security & Privacy page | https://www.zoom.com/en/products/ai-assistant/resources/privacy-security/ | redirects; content moved to library.zoom.com | public — **⚠️ re-locate** | C15 |
| E-07 | Zoom ISO 27001 page + Schellman certificate directory (cert 1407508-7) | https://www.zoom.com/en/trust/legal-compliance/iso-27001/ | ISO/IEC 27001:2022, issued 2026-02-17 | public (certificate); SoA gated | C01, C16 |
| E-08 | CSA STAR Registry — Zoom | https://cloudsecurityalliance.org/star/registry/services/zoom-video-communications-inc | CAIQ v4.0.2 (2022-09-19); STAR Level 2 v4.0 (2025-04-29); all flagged "deprecated / not updated within validity period" | listing public; documents not retrieved | C16, F-02 |
| E-09 | Zoom Security & Compliance FAQ | https://www.zoom.com/en/trust/legal-compliance/faq/ | live page | public | C16 |
| E-10 | Zoom Vulnerability Disclosure Policy | https://www.zoom.com/en/trust/reporting-vulnerability/ | live page | public | C08 |
| E-11 | Zoom bug bounty program (HackerOne) | https://hackerone.com/zoom | live | public | C08 |
| E-12 | Zoom Security Bulletins | https://www.zoom.com/en/trust/security-bulletin/ | live | public | C08, C09 |
| E-13 | Zoom Global Data Processing Addendum (DPA) | https://media.zoom.com/download/assets/zoom-global-dpa.pdf/dd327ebea27e11efb613d6ba63ed4cee | version/date on PDF cover — **⚠️ record** | public | C10, C12, C13 |
| E-14 | Zoom support — Selecting data center regions | https://support.zoom.us/hc/en-us/articles/360042411451 | live | public | C13 |
| E-15 | Zoom support — "Managing cloud recording settings" (KB0065362) | https://support.zoom.com/hc/en/article?id=zm_kb&sysparm_article=KB0065362 | live, undated | public | C12 |
| E-16 | Zoom blog — "Secure your Zoom account with two-factor authentication" (admin-level 2FA enforcement) | https://www.zoom.com/en/blog/secure-your-zoom-account-with-two-factor-authentication/ | 2020-09-10 | public | C04 |
| E-17 | Zoom status page + support response times (KB0059100, P1–P4 severity) | https://status.zoom.us/ ; https://support.zoom.com/hc/en/article?id=zm_kb&sysparm_article=KB0059100 | live | public | C11 |
| E-17b | Zoom Availability SLA (99.9% monthly target, excluding excused downtime) | Zoom legal/SLA document — **⚠️ record URL** | — | public | C11 |
| E-18 | Zoom SOC 2 Type II report and bridge letter | via trust.zoom.com | — | **gated — not obtained** | C16 → F-01 |
| E-19 | Zoom CAIQ (current) and SIG Core questionnaire | via trust.zoom.com | — | **gated — not obtained** | C01–C03, C07, C09 |
| E-20 | MSG91 SOC 2 Type 2 report (practice reading only, not Zoom) | https://msg91.com/pdf/soc2.pdf | period 2024-01-26 → 2024-04-26; 52 pp. | public | 05-soc2-triage.md |

Rows marked **⚠️** have a URL or date still to be recorded; they do not affect any finding. Do not commit gated documents to this repository.
