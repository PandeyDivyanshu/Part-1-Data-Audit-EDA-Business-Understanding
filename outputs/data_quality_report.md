# Data Quality Report

Snapshot date: **2025-09-30**

## 1) Missing Values

| Table | Column | Missing Count | Missing % |
|---|---|---:|---:|
| customers | loyalty_tier | 1386 | 57.8% |
| customers | skin_type | 401 | 16.7% |
| orders | rating | 80 | 0.8% |
| support_tickets | _No missing columns_ | 0 | 0.0% |
| web_events_snapshot | _No missing columns_ | 0 | 0.0% |
| rfm_modeling_snapshot | loyalty_tier | 1386 | 57.8% |
| intervention_history | _No missing columns_ | 0 | 0.0% |

## 2) Duplicates

- Orders with `_DUP` suffix: **12**
- Duplicate customer IDs in `customers`: **0**

## 3) Date Consistency and Leakage Risk

- Pre-snapshot orders (feature-safe): **8,137**
- Post-snapshot orders (must not be model features): **1,872**

## 4) Outliers

- `gross_amount` p99: **2,309 INR**
- Rows above p99: **101**

## 5) Join-Key Integrity

- Order customer IDs not in customers: **0**
- Ticket customer IDs not in customers: **0**
- Web customer IDs not in customers: **0**
- Customers with no tickets (valid state): **1153**

## 6) Recommended Guardrails

- Remove `_DUP` rows before feature aggregation.
- Enforce `order_date <= snapshot_date` for all feature pipelines.
- Impute missing categorical values with explicit categories like `None/Unknown`.
- Cap/log-transform heavy-tailed monetary values before modeling.
