\# Bank churn: who leaves, and how much money leaves with them



\*\*Question:\*\* which customers of a bank are most likely to churn, and where is the money at risk?



\*\*Data:\*\* Kaggle "Churn Modelling" dataset, 10,000 customers, 14 columns (\[Churn Modelling dataset on Kaggle](https://www.kaggle.com/datasets/aakash50897/churn-modelling)). The raw file is not included; download it and save it as `data/raw/churn.csv`.



\## Key findings

\- 20.4% of customers churned (2,037 of 10,000). Every group is compared with this baseline.

\- Strongest signals: age (churn peaks at 56.0% for ages 50-59), number of products (2 products 7.6%, 3 products 82.7%, 4 products 100% on only 60 customers), inactivity (26.9% vs 14.3%), Germany (32.4% vs about 16% in France and Spain) and gender (women 25.1% vs men 16.5%).

\- Credit card ownership, credit score and tenure barely matter (negligible effect sizes).

\- Hypotheses written before testing: H1 failed (inactive members churn 1.88x as much, CI 1.74 to 2.05, not more than 2x), H2 held (ages 40-59: 37.1% vs 10.0%), H3 held (3+ products: 85.9% vs 18.2%).

\- Inactivity matters far more for older customers: inactive customers aged 50-59 churn at about 81% vs about 37% for active ones.

\- Revenue at risk (balance of churned customers x an assumed 3% margin): three inactive segments (ages 40-49, 50-59, 30-39) hold 55% of the balance at risk. Same top 3 at 2% and 4% margin.

\- Recommendation: target inactive customers aged 50-59 first, then inactive customers aged 40-49.



\## Method

Hypotheses first, Wilson confidence intervals, effect sizes (lift, Cramer's V, rank-biserial) because almost every p-value is tiny at 10,000 rows, bootstrap interval for a rate ratio, segment heatmaps, and a revenue-at-risk proxy with a Pareto chart.



\## Files

\- `notebooks/01\_eda.ipynb`: the analysis

\- `docs/insights\_log.md`: findings with evidence, so-what and next action

\- `docs/assumptions.md`: every assumption made

\- `docs/hypotheses.md`, `docs/data\_dictionary.md`

\- `docs/pareto\_revenue\_at\_risk.png`



\## Reproduce

1\. Download the dataset to `data/raw/churn.csv`

2\. `pip install -r requirements.txt`

3\. `python -m notebook` and open `notebooks/01\_eda.ipynb`



\## Limitations

Associations in one snapshot, not proof of cause. Revenue at risk is a proxy (balance x assumed margin), not actual bank revenue, and zero-balance customers contribute nothing to it. The churn window is not stated. Segments were picked after looking at several pairs, so treat them as leads.



\## Roadmap (pending)

\- SQL replication of the analysis

\- Excel pivot workbook

\- Tableau dashboard

\- Campaign breakeven with real costs

\- Predictive modelling

