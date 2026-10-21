# PesaPap Growth Analytics

## Project Summary

This project analyses PesaPap's transaction growth, customer behaviour and onboarding experiment using SQL, pandas and inferential statistics. The analysis answers key growth questions, builds a KPI scorecard, segments customers with RFM analysis, measures cohort retention and evaluates whether the simplified onboarding screen should be rolled out.

## Database Tables

### users
- Primary key: `user_id`
- Contains each user's signup date, county and acquisition channel.

### transactions
- Primary key: `txn_id`
- Foreign key: `user_id` references `users.user_id`
- Contains transaction date, product and transaction amount.

### experiment
- Primary key: `user_id`
- Foreign key: `user_id` references `users.user_id`
- Contains experiment group assignment and conversion outcome.

## How to Run

1. Run `generate_data.py` to create `users.csv`, `transactions.csv` and `experiment.csv`.
2. Open `pesapap_analysis.ipynb`.
3. Restart the kernel and run all cells from top to bottom.
4. The notebook builds `pesapap.db`, runs all SQL queries, calculates KPIs, performs RFM and cohort analysis, and evaluates the onboarding experiment.
5. SQL queries are also stored in `sql/queries.sql`.
6. The final growth recommendation is available in `reports/growth_memo.md`.

## Headline Recommendation

Roll out the simplified onboarding screen. Group B achieved a 13.81% conversion rate compared with 10.46% for group A, representing a 31.96% relative lift and a 3.34 percentage-point absolute increase. The result was statistically significant with p = 0.0061, and the 95% confidence interval for the lift was 1.01 to 5.67 percentage points. Assuming 10,000 monthly sign-ups, the new flow could generate roughly 334 additional converted users per month. After rollout, PesaPap should continue monitoring conversion and retention while targeting At risk customers with re-engagement campaigns.
