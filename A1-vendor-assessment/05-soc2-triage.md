# How I Tell a SOC 2 Exception from Noise

> ✍️ **To do (A1-09, A1-10):** read the publicly posted MSG91 SOC 2 Type 2 report (https://msg91.com/pdf/soc2.pdf), then fill every blank below in your own words.

## Practice report facts
| Fact | Value | Page |
|---|---|---|
| Opinion type (unqualified / qualified) | | |
| Observation period | | |
| Trust Services Criteria in scope | | |
| Subservice organizations (carve-out / inclusive) | | |
| Tests with exceptions | | |

## My five triage criteria
1. **Relevance to my use case:** is the failed control one my data or service actually depends on?
2. **Deviation rate vs sample size:** 1 miss in 25 samples is different from 5 in 25.
3. **Management response:** was the root cause fixed, and by when?
4. **Compensating controls:** does another tested control cover the same risk?
5. **Period coverage and staleness:** how long was the observation period, and does it reach today? If not, request a bridge letter.

> ✍️ Write 150–250 words applying these criteria to the practice report. A clean report ("no exceptions noted") can still carry risk, so look at the period length and date, the carve-outs, and the CUECs.

## CUECs a bank would have to operate itself
> ✍️ List 5 complementary user entity controls Banco Ejemplo would need for Zoom. Example: enforce SSO and MFA on the bank's Zoom account.
