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







\- Zero balances (36.2% of customers) are treated as genuine zero-balance accounts, not missing data.

\- Age outliers (359 customers beyond the IQR fence, max 92) are plausible real customers, so they are kept.

\- The CreditScore pile-up at 850 looks like a cap on the score scale; the values are kept as they are.

\- NumOfProducts 3 and 4 are very small groups (2.7% and 0.6%), so conclusions about them are low-confidence.





\- Age bands: <30 (18-29), 30-39, 40-49, 50-59, 60+. CreditScore bands are quintiles (Q1 lowest). Balance bands are Zero plus quartiles of the non-zero balances (Q1 lowest).

\- Effect sizes lead the interpretation because with 10,000 rows almost every test is significant: lift, Cramer's V (categorical) and rank-biserial (numeric).

\- A group is called above or below baseline only when its whole 95% interval sits on one side of 20.4%.

\- All findings are associations. Features overlap (for example balance, country and product count), so no single feature is shown to cause churn.





\- Effect-size labels used as rough rules of thumb: about 0.1 small, 0.3 medium, 0.5 large (Cramer's V and rank-biserial). They are not strictly comparable across the two measures.

\- Rank-biserial measures an overall tendency (churners higher or lower) and understates humped relationships such as Age and Balance; the charts are the better guide for those.

