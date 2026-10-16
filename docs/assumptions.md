\- Dataset: Kaggle Churn Modelling file, saved as bank-churn/data/raw/churn.csv. 10,000 customers, 14 columns.

\- Data checks passed: 0 missing values and 0 duplicate CustomerId values.

\- Exited = 1 means the customer churned. Churn rate = share of customers with Exited = 1.

\- The data year is not stated in the file. Treated as a single snapshot with no time dimension.

\- H1 groups: IsActiveMember = 0 (inactive) vs 1 (active).

\- H2 groups: age 40-59 vs under 40. Customers aged 60 and over (526 people, 147 churned) are left out of this comparison.

\- H3 groups: 3 or more products vs 1 or 2 products.

\- Significance threshold: p < 0.05. Rates carry 95% Wilson confidence intervals.

\- Group differences tested with a chi-square test. The H1 rate ratio uses a bootstrap (5,000 resamples, random seed 42) for its 95% CI.

\- Results show association, not causation. No other variables are controlled for yet.

\- If the Kaggle licence is unclear, data/raw/ stays out of Git (.gitignore) and the download link goes in the README.



\- RowNumber, CustomerId and Surname are identifiers with no business meaning, so they are excluded from the analysis and from any modelling. The raw file is not changed.

