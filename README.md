# DocuSign Self-Serve Retention Case Study

Analysis identifying the top opportunities to improve self-serve customer retention at DocuSign.

---

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

Templates signal workflow integration — DocuSign embedded into how the customer operates.

**3. Passive churn is recoverable**

| Churn Type | ARR Lost |
|------------|----------|
| Active (deliberate cancellation) | $2.33M |
| Passive (billing/payment failure) | $1.73M |

42% of churned accounts left because a card expired — not because they chose to. These are recoverable without product changes.

**4. Annual billing nearly halves churn**

Monthly → 42% churn | Annual → 23% churn. Annual subscribers self-select as higher intent and face higher switching friction.

---

## Recommendations

### 1. Reduce passive churn (~$520K ARR opportunity)
Implement pre-expiry card reminders, automated dunning retries, and grace periods before cancellation. Assuming 30% recovery on $1.73M passive churn ARR.

### 2. Improve early activation (~$170K ARR opportunity, conservative)
The zero-send segment (4,405 accounts, 45% churn, $382K ARR at risk) never reached the first meaningful product moment. A guided first-send onboarding flow and early lifecycle nudges targeting the 20-send threshold is the entry point. Full low-engagement population (<20 sends) represents $1.82M in churned ARR.

| Opportunity | Estimated ARR Preserved | Effort | Confidence |
|-------------|------------------------|--------|------------|
| Passive churn recovery | ~$520K | Low | High |
| Activation improvement | ~$170K (floor) | Medium | High |

---

## Deliverables

- `docusign_retention_case_duckdb.ipynb` — full analysis notebook
- `renato perez - docusign_retention_case_slides.pptx` — 6-slide presentation deck
