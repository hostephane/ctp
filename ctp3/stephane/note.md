# Data Dictionary Notes — `stg_orders` & `stg_payments` (Differences vs. Code)

Comparing `data_dictionary_template.csv` and `dbt show --select stg_payments --limit 5` against `data_dictionary_from_dbt.csv` (generated from dbt metadata/YAML):

1. **Column-level governance & operational fields not yet in YAML/code:**
   - `nullable_Y_N`, `example_value`, `personal_data_Y_N`, `classification` (on payment/order columns), and `source_system` are captured in the dictionary/mental model, whereas `data_dictionary_from_dbt.csv` only reflects what is currently modeled/documented in dbt YAML/catalog.
2. **Business rules & ranges not yet enforced as dbt tests:**
   - Value ranges and format rules (such as `>= 0` / positive IDs, `card_last4` 4-digit format, or payment method/currency constraints) are documented in the dictionary rather than all encoded as active dbt tests.
3. **Unit alignment (`stg_payments.amount`):**
   - `stg_payments.amount` is now documented in Euro cents in `data_dictionary_from_dbt.csv` (`divide by 100 for EUR`), and `data_dictionary_template.csv` has been updated accordingly, while downstream range/scale tests can still be strengthened.