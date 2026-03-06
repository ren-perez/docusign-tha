# DocuSign Self-Serve Retention Analysis — Findings

**Data snapshot:** January 31, 2017 | **Post-snapshot churn window:** through Feb 2018

---

## 1. Baseline

| Metric | Value |
|---|---|
| Total accounts | 56,062 |
| Total MRR | $1,343,948 |
| Total ARR | $16,127,371 |
| Churned accounts | 15,174 (27.1%) |
| Churn MRR | -$338,086 |
| Churn ARR | -$4,057,030 |
| MRR Churn Rate | **-25.2%** |

---

## 2. Active vs. Passive Churn

| Type | Accounts | Churn ARR |
|---|---|---|
| Active churn | 8,845 | -$2,328,305 |
| Passive churn | 6,329 | -$1,728,726 |

- Active churn is the larger problem by volume and ARR.
- Passive churn (~42% of churned accounts) represents recoverable revenue via billing/dunning improvements.

---

## 3. Usage vs. Churn — The Core Signal

### Lifetime Sends

| Sends | Accounts | Churn Rate | Churn ARR |
|---|---|---|---|
| 0 | 4,405 | 45.4% | -$382,830 |
| 1–5 | 5,630 | 49.1% | -$598,495 |
| 6–20 | 7,166 | 50.6% | -$836,360 |
| 20+ | 38,861 | **17.5%** | -$2,239,346 |

**Key insight:** Accounts with 20+ sends churn at 17.5% vs. 45–51% for low-usage accounts. Heavy users are 3x stickier. Churn rate is highest in the 6–20 send bucket, suggesting users are trying but not converting into habitual use.

### Completed Transactions (LIFETIMEST)

| Completed | Accounts | Churn Rate | Churn ARR |
|---|---|---|---|
| 0 | 5,365 | 46.8% | -$500,581 |
| 1–5 | 6,944 | 50.2% | -$773,212 |
| 6–20 | 7,269 | 47.5% | -$862,114 |
| 20+ | 36,484 | **15.7%** | -$1,921,124 |

Mirrors the sends pattern — value realization (completed agreements) is the strongest retention predictor.

### Template Creation

| Segment | Accounts | Churn Rate | Churn ARR |
|---|---|---|---|
| Has templates | 3,092 | **13.4%** | -$195,313 |
| No templates | 52,970 | 27.9% | -$3,861,717 |

Template users churn at half the rate. Templates are a strong stickiness signal — likely a power-user proxy.

---

## 4. Plan Family

| Plan | Accounts | Churn Rate | Churn ARR |
|---|---|---|---|
| Business | 13,575 | 21.6% | -$1,484,495 |
| Standard | 12,609 | 24.0% | -$1,139,517 |
| Personal | 18,795 | **36.2%** | -$944,456 |
| Real Estate | 11,083 | 21.7% | -$488,563 |

- **Personal plan** has the highest churn rate (36.2%) — likely low-commitment, single-user accounts.
- Business plan drives the most churn ARR despite a lower rate, due to higher MRR per account.

---

## 5. Billing Cycle

| Cycle | Accounts | Churn Rate | Churn ARR |
|---|---|---|---|
| Monthly | 12,354 | **42.1%** | -$1,780,361 |
| Annual | 43,708 | 22.8% | -$2,276,670 |

Monthly subscribers churn at nearly 2x the rate of annual subscribers. Converting monthly to annual is a high-leverage retention lever.

---

## 6. Industry (Top 10 by Churn ARR)

| Industry | Accounts | Churn Rate | Churn ARR |
|---|---|---|---|
| Construction | 2,405 | 22.7% | -$154,339 |
| Healthcare | 1,731 | 28.1% | -$150,704 |
| Insurance | 1,735 | 21.2% | -$119,921 |
| Mortgage | 1,637 | 18.4% | -$105,734 |
| Education | 1,082 | 32.6% | -$97,411 |
| Legal | 1,668 | 19.8% | -$92,924 |
| Accounting | 952 | 24.9% | -$68,571 |
| Not for Profit | 710 | 29.9% | -$59,317 |
| Life Sciences | 408 | 26.2% | -$36,850 |
| Government | 234 | 38.0% | -$19,289 |

- **Construction** and **Healthcare** drive the most churn ARR.
- **Government** and **Education** have elevated churn rates (38%, 32.6%) relative to their size.

---

## 7. Opportunity Sizing

| Opportunity | Mechanism | Recoverable ARR |
|---|---|---|
| Activation (zero-send accounts) | Reduce churn rate by 20pp in the 0-send segment | ~$169K |
| Passive churn recovery | Dunning / billing retry at 30% recovery rate | ~$519K |
| Monthly-to-annual conversion | Structural (not sized here) | High leverage |
| Template adoption | Drive template creation as activation milestone | High leverage |

---

## Key Takeaways

1. **Usage is the #1 churn predictor.** 20+ sends = 17.5% churn. Under 20 sends = 45–51% churn. Getting users to habitual use is the core retention problem.
2. **Templates are a power signal.** 13.4% churn rate for template users vs. 27.9% for non-users. Template creation should be a key activation milestone.
3. **Passive churn is large and recoverable.** $1.7M ARR lost passively — dunning improvements could recover ~$500K.
4. **Monthly billing is a risk flag.** 42% churn rate vs. 23% annual. Annual commitment drives retention.
5. **Personal plan needs attention.** Highest churn rate (36.2%) across plans — likely structural to the low-engagement single-user profile.
