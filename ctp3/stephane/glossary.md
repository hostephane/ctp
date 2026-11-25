{% docs gross_revenue %}
**Gross revenue (EUR)** — total amount paid by the customer for an order, VAT included, shipping included, before refunds.
Owner: Head of Sales · Steward: Karim Benali · Status: approved (2026-11-10)
{% enddocs %}

{% docs net_revenue %}
**Net revenue (EUR)** — order revenue excluding VAT and after refunds, keeping shipping fees (excluding cancelled orders).
Owner: Head of Finance · Steward: Karim Benali · Status: approved (2026-11-25)
{% enddocs %}

{% docs active_customer %}
**Active customer** — customer account with at least one non-cancelled order in the last 12 rolling months (a 6-month view/filter is kept separately for Sales campaigns).
Owner: Head of Finance · Steward: Karim Benali · Status: approved (2026-11-25)
{% enddocs %}

{% docs churned_customer %}
**Churned customer** — customer account with at least one past order (`lifetime_orders > 0`) and no non-cancelled order in the last 12 rolling months.
Owner: Head of Finance & Head of Sales · Steward: Karim Benali · Status: draft (2026-11-25)
{% enddocs %}

{% docs order %}
**Order** — a customer purchase transaction on ShopFast with a lifecycle status and order amounts.
Owner: Head of Sales · Steward: Karim Benali · Status: approved (2026-11-25)
{% enddocs %}

{% docs customer %}
**Customer** — customer account record (`customer_id`) in ShopFast (one person may have multiple accounts).
Owner: Head of Sales · Steward: Karim Benali · Status: approved (2026-11-25)
{% enddocs %}

{# TODO (Exercise 3): add the terms net_revenue, active_customer, churned_customer, order, customer #}