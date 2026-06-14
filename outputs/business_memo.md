# Business Memo - Churn Early Signals

## Context

Analyzed **2,400** customers at snapshot date **2025-09-30**; churn base rate is **47.0%** (1,127 customers).

## Priority Findings

1. **Recency risk**: churn is **11.7%** for recency <= 30 days vs **90.9%** for recency > 150 days (Chart 3).
2. **Support friction**: churn is **50.6%** for 0 tickets vs **0.0%** for 3+ tickets (Charts 4 and 7).
3. **Return behavior**: churn is **47.2%** at 0% return rate vs **53.3%** when return_rate_180d > 30% (Chart 5 left).
4. **Engagement drop**: churn is **64.5%** when sessions_30d <= 2 vs **27.4%** when sessions_30d >= 8 (Chart 6).
5. **Discount dependency**: churn is **46.8%** for avg_discount_pct >= 40% vs **60.7%** for < 20% (Chart 5 right).
6. **Channel quality**: highest churn channel is **Google Search** (50.4%) vs lowest **Organic** (39.8%) (Chart 8).

## Recommended Investigation Order

1. Resolve high-ticket support issues before discounting.
2. Trigger reactivation before customers cross 90-day recency.
3. Diagnose product-fit issues for high-return cohorts.
4. Use value-led messaging for discount-dependent customers.
5. Build channel-specific onboarding and retention plays.
