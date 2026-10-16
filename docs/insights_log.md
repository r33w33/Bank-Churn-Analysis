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





\## Churn by feature (Block 1.5), baseline 20.4%



| Finding | Evidence (number) | So what | Next action |

|---|---|---|---|

| Germany churns at about twice the rate of France and Spain | Germany 32.4% (n=2,509, 95% CI 30.6% to 34.3%) vs France 16.2% and Spain 16.7%; lift 1.59 | Germany is the only country above baseline | Check whether balance or product mix explains the gap |

| Women churn more than men | Female 25.1% (n=4,543) vs male 16.5%; lift 1.23 vs 0.81 | Association only; intervals are clear of baseline in both directions | Check whether the gap holds within each country and age band |

| Product count is not linear: 2 products is safest, 3 or more is extreme | 1 product 27.7%, 2 products 7.6%, 3 products 82.7% (n=266), 4 products 100% (n=60) | Holders of 3 or 4 products are almost certain to leave, but the groups are small | Investigate why; do not assume more products causes churn |

| Inactive members churn about 1.9x active members | Inactive 26.9% vs active 14.3%; lift 1.32 vs 0.70 | Inactivity is a clear warning sign | Use as a segmentation flag |

| Churn peaks at ages 50-59 | <30 7.6%, 30-39 10.9%, 40-49 30.8%, 50-59 56.0% (n=869), 60+ 27.9% | Risk rises sharply after 40, then falls after 60 | Profile the 50-59 group (products, balance, activity) |

| Having a credit card makes no difference | With card 20.2% vs without 20.8%; both intervals include the baseline | Not a useful predictor | Drop from segmentation |

| Credit score has a weak effect | Q1 22.5% (CI 20.7% to 24.4%) down to Q4 18.3% (CI 16.7% to 20.1%) | Differences are small and only just clear the baseline | Check effect size in the rank-biserial output |

| Zero-balance customers churn less than those with a balance | Zero balance 13.8% (n=3,617) vs balance Q2 27.4%, Q3 25.3%, Q4 23.0%; Q1 20.6% is close to baseline | A balance on the account goes with higher churn | Check overlap with Germany and with product count |



Hypothesis results: H1 failed (ratio 1.88, 95% CI 1.74 to 2.05, does not clear 2x). H2 held (40-59 churn 37.1% vs 10.0% under 40). H3 held (3 or more products 85.9% vs 18.2%), with the caveat that the group is small and 2 products is the lowest-churn group.

