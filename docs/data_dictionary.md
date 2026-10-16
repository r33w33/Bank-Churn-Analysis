\# Data dictionary: Kaggle Churn Modelling



10,000 customers, 14 columns. One row per customer.



| Column | Type | Meaning | Allowed values |

|---|---|---|---|

| RowNumber | int | Row index in the file; no business meaning | 1 to 10,000 |

| CustomerId | int | Unique customer ID | 10,000 unique values |

| Surname | text | Customer surname; not used in analysis | free text |

| CreditScore | int | Customer's credit score | about 350 to 850 |

| Geography | text | Country the customer lives in | France, Germany, Spain |

| Gender | text | Customer's gender | Female, Male |

| Age | int | Age in years | 18 to 92 |

| Tenure | int | Years the customer has been with the bank | 0 to 10 |

| Balance | float | Account balance (0 means a zero-balance account) | 0 and above |

| NumOfProducts | int | Number of bank products the customer holds | 1 to 4 |

| HasCrCard | int (flag) | Holds a credit card with the bank | 0 = no, 1 = yes |

| IsActiveMember | int (flag) | Counted as an active member | 0 = inactive, 1 = active |

| EstimatedSalary | float | Estimated annual salary of the customer (not bank revenue) | positive numbers |

| Exited | int (flag) | Target: customer left the bank | 0 = stayed, 1 = churned |



\## Baseline

Baseline churn rate: 20.4% (2,037 of 10,000). Every segment is judged against this.

