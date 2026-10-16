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







\## Effect sizes (Block 1.5)



| Feature | Test result | Effect size | Verdict |

|---|---|---|---|

| Age | p < 0.001 | rank-biserial 0.46 | Strongest signal; churn peaks at ages 50-59 |

| NumOfProducts | p < 0.001 | Cramer's V 0.39 | Strong; 2 products safest, 3 or more extreme |

| Geography | p < 0.001 | Cramer's V 0.17 | Small; driven by Germany |

| IsActiveMember | p < 0.001 | Cramer's V 0.16 | Small; inactive members churn more |

| Balance | p < 0.001 | rank-biserial 0.16 | Small; zero-balance customers churn least |

| Gender | p < 0.001 | Cramer's V 0.11 | Small; women churn more |

| CreditScore | p = 0.02 | rank-biserial -0.03 | Negligible despite p < 0.05 |

| Tenure | p = 0.16 | rank-biserial -0.02 | Negligible and not significant |



Ranking by effect size: Age, NumOfProducts, then Geography, IsActiveMember and Balance (small), Gender (small), and CreditScore and Tenure (negligible). With 10,000 rows, p-values alone do not separate strong features from weak ones.







\## Segments and interactions (Block 1.6), baseline 20.4%



| Finding | Evidence (number) | So what | Next action |

|---|---|---|---|

| Top segment 1: inactive customers aged 50-59 | About 81% churn (n=373) vs 37% for active customers aged 50-59 | Highest-risk large segment; inactivity drives it | Confirm exact interval with the segment table |

| Top segment 2: customers with 3 products | About 83% churn (n=266): 88% if inactive (n=153), 75% if active (n=113) | Extreme churn regardless of activity; small group | Investigate why; may reflect product mix or mis-selling |

| Top segment 3: women in Germany | About 38% churn (n=1,193) vs 28% for men in Germany and 20-21% for women in France and Spain | Germany raises churn for both genders; gender gap appears in every country | Check whether balance or product mix explains Germany |

| Inactivity matters more with age | Inactive vs active: under 30 10% vs 5%; 40-49 38% vs 23%; 50-59 81% vs 37%; 60+ 86% (n=111) vs 13% | Older inactive customers are the real risk; older active customers are not | Use age x activity as a targeting rule |

| 2 products is the safest holding | 10% if inactive, 6% if active | Not simply 'more products is better': the pattern is a U-shape | Compare with 3 products |

| Largest churn volume sits in large moderate-rate groups | Inactive 40-49: about 38% on n=1,396 (roughly 530 churners) | Highest rate is not the same as most customers lost | Size segments by customers lost as well as rate |

| No two numeric columns are strongly correlated | No pair above 0.5; strongest is Balance vs NumOfProducts at -0.30 | No redundant features | None needed |

| Linear correlation hides the product pattern | NumOfProducts vs Exited correlation is -0.05 despite Cramer's V of 0.39 | Do not rely on correlation for non-linear effects | Use group rates for non-linear features |



Segments with fewer than 100 customers were ignored (including 4 products, n=60, all churned).





















\## Revenue at risk (Blocks 1.7 and 1.8), NIM 3%



| Finding | Evidence (number) | So what | Next action |

|---|---|---|---|

| Three inactive segments hold 55% of balance at risk | Inactive 40-49 (25.8%), inactive 50-59 (14.6%), inactive 30-39 (14.4%); total balance at risk 185.6M, revenue proxy 5.57M | Money at risk is concentrated in a few segments | Focus retention effort on these first |

| Largest single pot: inactive customers aged 40-49 | 47.8M balance at risk, 25.8% share, 38.0% churn, n=1,396 | Biggest absolute loss, with a moderate churn rate | Prioritise for retention |

| Rate and money rankings disagree | Inactive 60+: highest churn (85.6%, n=111) but 7th by money (4.7%). Inactive 30-39: churn only 13.6% but 3rd by money (14.4%) | Churn rate alone misleads; size and balance decide the money | Rank segments by both rate and balance at risk |

| Inactive customers carry about 64% of revenue at risk | Five inactive segments = 63.8% of the 5.57M proxy | Inactivity is the main lever | Test re-engagement before offers |

| Targeting order does not depend on NIM | Same top 3 at 2%, 3% and 4%; total proxy 3.71M, 5.57M, 7.42M | NIM changes the size of the figure, not the ranking | Keep NIM as a stated assumption |

| Zero-balance churners are invisible to the proxy | 500 of 2,037 churners (24.5%) have a zero balance | Proxy understates customer-count loss | Report churner counts next to revenue at risk |



Recommendation (base NIM 3%): target inactive customers aged 50-59 first (81% churn, 373 customers, 14.6% of revenue at risk, about 2,185 balance units at risk per customer), then inactive customers aged 40-49, the largest single pot at 25.8%.



The revenue figure is a proxy built from balance and an assumed margin, not actual bank revenue. Customers with zero balance contribute nothing to it.

