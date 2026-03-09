# Docusign Self-Serve Retention Case Study

**Objective:** Identify and size the top opportunities to improve self-serve customer retention.


## Dataset

Three tables joined on `ACCOUNTID`:

| Table | Description |
|-------|-------------|
| Customer base snapshot (Jan 31, 2017) | 56,062 active self-serve accounts; $16.1M total ARR |
| Churn transactions (post-snapshot) | All churn events in the observation window |
| Usage data (Feb 1, 2018) | Lifetime sends, completions, templates, PowerForms per account |

Analysis conducted in Python + DuckDB. See `docusign_retention_case_duckdb.ipynb`.

---

## Baseline Metrics

| Metric | Value |
|--------|-------|
| Total accounts | 56,062 |
| Total ARR | $16.1M |
| Churned accounts | 15,174 (27%) |
| Churned ARR | $4.06M (25% ARR churn rate) |

---

## Key Findings

**1. Product usage is the primary retention driver**

| Lifetime Sends | Churn Rate |
|----------------|------------|
| 0 | 45% |
| 1–20 | ~49–51% |
| 20+ | **17%** |

Getting a customer to 20 sends cuts churn by ~3x. This is the activation threshold.

**2. Templates are the stickiest behavior**

| Segment | Churn Rate |
|---------|------------|
| Created ≥1 template | 13.4% |
| No templates | 27.9% |

If someone built a template, Docusign is part of their actual workflow. That's when they stop leaving.

**3. Passive churn is recoverable**

| Churn Type | ARR Lost |
|------------|----------|
| Active (deliberate cancellation) | $2.33M |
| Passive (billing/payment failure) | $1.73M |

42% of churned accounts left because a card expired. Not a product problem — just a billing one. These are recoverable without product changes.

**4. Annual billing nearly halves churn**

Monthly → 42% churn | Annual → 23% churn. Annual customers are just more committed — they paid upfront and switching costs more.

---

## Recommendations

### 1. Reduce passive churn (~$520K ARR opportunity)
Implement pre-expiry card reminders, automated dunning retries, and grace periods before cancellation. Assuming 30% recovery on $1.73M passive churn ARR.

### 2. Improve early activation (~$170K ARR opportunity, conservative)
4,405 accounts never sent a single document — 45% of them churned, putting $382K ARR at risk. They signed up and never actually used it. A better onboarding flow that gets people to that first send (and pushes toward 20) is where to start.

| Lifetime Sends | Accounts | Churn Rate | Churned ARR |
|----------------|----------|------------|-------------|
| 0 | 4,405 | 45% | $383K |
| 1–5 | 5,630 | 49% | $598K |
| 6–20 | 7,166 | 51% | $836K |
| **Total <20 sends** | **17,201** | | **$1.82M** |

The full low-engagement group (<20 sends) represents $1.82M in churned ARR — the ceiling of this opportunity. The conservative $170K estimate assumes a 20pp churn reduction in the zero-send segment only.

| Opportunity | Estimated ARR Preserved | Effort | Confidence |
|-------------|------------------------|--------|------------|
| Passive churn recovery | ~$520K | Low | High |
| Activation improvement | ~$170K (floor) | Medium | High |

---

## Deliverables

- `docusign_retention_case_duckdb.ipynb` — full analysis notebook
- `renato perez - docusign_retention_case_slides.pptx` — 6-slide presentation deck
