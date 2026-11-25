Subject: Impact notice — Payment `amount` unit change (EUR -> cents) on `source:shopfast_raw.payments`

1. What breaks: `stg_payments` will ingest values 100x larger if units shift to cents without alignment, breaking `fct_orders` (`refunded_eur`, `net_revenue_eur`), `dim_customers` (`lifetime_net_revenue_eur`), `finance_monthly_revenue_report`, `sales_dashboard`, and `churn_prediction_ml_model`.
2. Owners to warn: Claire Dubois (`finance_monthly_revenue_report` / Finance), Sara Martin (`sales_dashboard` / Sales), and Karim Benali (steward / `churn_prediction_ml_model`).
3. Test to add: add a range/unit check on `stg_payments.amount` and `fct_orders.net_revenue_eur` (e.g. `dbt_utils.expression_is_true` or `expect_column_values_to_be_between`) to catch 100x / unit mismatches before load completes.
4. Who approves the change: Claire Dubois (Finance owner) and Sara Martin (Sales/Customer owner), coordinated with Karim Benali (steward).
5. Verification before cutover: test in staging/dev, run `dbt build` and `dbt docs generate`, and verify downstream nodes via `dbt ls --select source:shopfast_raw.payments+`.