| Finding | Evidence (number) | So what | Next action |

|---|---|---|---|

| Baseline churn | 2,037 of 10,000 = 20.4% | About 1 in 5 customers leaves; benchmark for all segments | Use 20.4% as benchmark in charts |

| H1 disproved: inactive churn \~1.9x active, not >2x | Inactive 26.9% vs active 14.3%; ratio 1.88, 95% CI \[1.74, 2.05]; p < 0.001 | Inactivity raises churn but does not clear the 2x bar | Report as 'nearly double'; test with age and products controlled |

| H2 supported: age 40-59 churn far more than under 40 | 37.1% vs 10.0%; p < 0.001 | Middle-aged customers are the largest at-risk age group | Chart churn by age band; profile these customers |

| H3 supported: 3+ products churn far more than 1-2 | 85.9% (n=326) vs 18.2%; p < 0.001 | More products does not mean more loyalty; small but extreme group | Break down by 1, 2, 3, 4 products |





\## Univariate notes (Block 1.4)



\- CreditScore: roughly bell-shaped (skew -0.07, median 652, range 350 to 850), with an extra pile-up at the 850 maximum and 15 low-end outliers.

\- Age: right-skewed (skew 1.01), median 37, most customers in their 30s and 40s; 359 customers beyond the IQR fence on the older side (max 92).

\- Tenure: close to flat from 1 to 9 years (about 1,000 customers per year), with fewer at 0 years (4.1% of customers) and at 10; skew 0.01.

\- Balance: 36.2% of customers have a zero balance, a spike far above everything else; the rest are roughly bell-shaped around 120,000, up to 250,898.

\- EstimatedSalary: almost perfectly flat from 11.58 to 199,992 (skew 0.00), which is unusual for real salaries and suggests it carries little signal.

\- Geography: France 50.1%, Germany 25.1%, Spain 24.8%.

\- Gender: Male 54.6%, Female 45.4%.

\- NumOfProducts: 1 product 50.8%, 2 products 45.9%, 3 products 2.7%, 4 products 0.6%.

\- HasCrCard: 70.6% hold a credit card with the bank, 29.4% do not.

\- IsActiveMember: 51.5% active, 48.5% inactive, a near even split.

\- Categories under 5% of customers: 3 products (2.7%) and 4 products (0.6%). Treat any rate for these groups with care because of the small numbers.

