# DocuSign Self-Serve Retention Case Study

Analysis to identify the **top opportunities to improve self-serve customer retention** at DocuSign using the provided dataset.

This repository contains:

* analysis notebooks and SQL queries
* summarized findings
* a 6-slide presentation with recommendations

---

# Objective

Identify and size the **1–2 highest impact opportunities** to improve self-serve retention.

Focus areas:

* churn drivers
* product usage behavior
* revenue impact (ARR)
* actionable product or lifecycle interventions

---

# Dataset

Three datasets were provided:

| Table                  | Description                                  |
| ---------------------- | -------------------------------------------- |
| customer base snapshot | Customer accounts and MRR as of Jan 31, 2017 |
| churn transactions     | Churn events after snapshot                  |
| usage data             | Lifetime product usage signals               |

Total accounts analyzed: **56,062**

---

# Methodology

Analysis was structured around a **retention lifecycle framework**.

1. Establish baseline churn metrics
2. Segment churn by customer attributes
3. Analyze product usage vs retention
4. Identify revenue-impactful churn segments
5. Estimate potential retention improvements

Key analysis dimensions:

* usage signals (sends, completed transactions)
* feature adoption (templates)
* plan type
* billing cycle
* industry segmentation
* churn type (active vs passive)

All data exploration was conducted using **Python + DuckDB SQL**.

---

# Baseline Metrics

| Metric            | Value        |
| ----------------- | ------------ |
| Accounts analyzed | 56,062       |
| Total ARR         | $16.1M       |
| Churned accounts  | 15,174 (27%) |
| Churn ARR         | $4.06M       |
| ARR churn rate    | 25.2%        |

---

# Key Insights

## 1. Product Usage Is the Strongest Retention Signal

| Lifetime Sends | Churn Rate |
| -------------- | ---------- |
| 0 sends        | 45%        |
| 1–5 sends      | 49%        |
| 6–20 sends     | 51%        |
| 20+ sends      | **17%**    |

Heavy users are **~3x more likely to retain**.

This indicates that retention is primarily driven by **value realization and habitual product use**.

---

## 2. Templates Are a Strong Engagement Signal

| Segment        | Churn Rate |
| -------------- | ---------- |
| Template users | **13.4%**  |
| No templates   | 27.9%      |

Templates likely represent workflow integration and repeat use.

---

## 3. Passive Churn Represents Recoverable Revenue

| Churn Type    | ARR    |
| ------------- | ------ |
| Active churn  | $2.33M |
| Passive churn | $1.73M |

Passive churn (~42% of churned accounts) often results from **payment failures** and can typically be recovered through billing improvements.

---

## 4. Monthly Billing Drives Higher Churn

| Billing Cycle | Churn Rate |
| ------------- | ---------- |
| Monthly       | **42%**    |
| Annual        | 23%        |

Monthly subscriptions show nearly **2x higher churn risk**.

---

# Recommended Opportunities

## Opportunity 1 — Improve Early Activation

Many users never reach meaningful product usage.

Target segment:

| Metric     | Value |
| ---------- | ----- |
| Accounts   | 4,405 |
| Churn rate | 45%   |
| Churn ARR  | $382K |

Proposed interventions:

* onboarding flows guiding first document send
* template recommendations during onboarding
* lifecycle nudges encouraging agreement completion

Estimated impact:

Assuming **20pp churn reduction**

Estimated ARR preserved: **~$170K**

---

## Opportunity 2 — Reduce Passive Churn

Passive churn accounts for **$1.73M ARR lost**.

Potential solutions:

* automated payment retries
* credit card expiration reminders
* in-product payment update prompts
* grace periods before cancellation

Estimated impact:

Assuming **30% recovery**

Estimated ARR preserved: **~$520K**

---

# Prioritization Logic

Opportunities were prioritized based on:

* revenue impact
* implementation feasibility
* strength of supporting signals

| Opportunity            | Impact     | Effort | Confidence |
| ---------------------- | ---------- | ------ | ---------- |
| Passive churn recovery | ~$520K ARR | Low    | High       |
| Activation improvement | ~$170K ARR | Medium | High       |

Together they address both:

* **revenue leakage**
* **long-term user engagement**

---

# Assumptions

Impact estimates rely on the following assumptions:

* activation improvements reduce churn by **20 percentage points** for zero-send users
* passive churn recovery rate of **~30%**
* lifetime usage metrics approximate customer value realization

These estimates are directional and intended to guide prioritization.

---

# Additional Data Requested

If this were a live project, further analysis would benefit from:

* time-to-first-send metrics
* cancellation reasons
* cancel-save flow performance
* feature-level product telemetry
* acquisition channel segmentation
* cohort-level lifecycle behavior

This would enable deeper **experimentation and retention modeling**.

---

# Deliverables

This project includes:

* SQL + Python analysis notebook
* summarized findings (`findings.md`)
* presentation deck (`slides.pptx`)
* this README overview

---

# Summary

Retention in DocuSign’s self-serve business appears primarily driven by **product usage and workflow integration**.

Two high-impact opportunities emerge:

1. **Improve activation to drive habitual usage**
2. **Recover revenue lost through passive churn**

Together these initiatives could preserve **~$700K ARR** and create a stronger foundation for long-term retention improvements.
