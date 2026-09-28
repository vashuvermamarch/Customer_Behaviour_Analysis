# Customer Shopping Behavior Analysis

An end-to-end data analytics project that explores customer shopping behavior using **Python**, **PostgreSQL** and **Power BI**. The analysis covers 3,900 purchases and looks at spending patterns, customer segments, product preferences and subscription behavior to support strategic business decisions.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Tech Stack](#tech-stack)
- [Workflow](#workflow)
- [SQL Business Questions](#sql-business-questions)
- [Key Findings](#key-findings)
- [Power BI Dashboard](#power-bi-dashboard)
- [Business Recommendations](#business-recommendations)
- [Project Structure](#project-structure)
- [How to Run](#how-to-run)
- [Author](#author)

---

## Project Overview

The goal of this project is to turn raw transactional data into actionable insights. It answers questions such as:

- Which customers and age groups generate the most revenue?
- How do subscribers differ from non-subscribers?
- Which products are top rated, best selling or heavily discount-dependent?
- How loyal is the customer base, and how can it be grown?

## Dataset

| Property | Value |
|---|---|
| Rows | 3,900 purchases |
| Columns | 18 |
| Missing data | 37 values in `Review Rating` |

**Feature groups**

- **Demographics:** Age, Gender, Location, Subscription Status
- **Purchase details:** Item Purchased, Category, Purchase Amount (USD), Season, Size, Color
- **Shopping behavior:** Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type, Payment Method

> Add a link to the dataset source here (e.g. Kaggle) if you are making the data public.

## Tech Stack

- **Python** (pandas) for data loading, cleaning and feature engineering
- **PostgreSQL** for structured business analysis with SQL
- **Power BI** for the interactive dashboard
- **Jupyter Notebook** for exploratory data analysis

## Workflow

### 1. Data preparation and EDA (Python)

- **Data loading:** imported the dataset with `pandas`.
- **Initial exploration:** used `df.info()` and `.describe()` to check structure and summary statistics.
- **Missing data handling:** imputed missing `Review Rating` values using the median rating of each product category.
- **Column standardization:** renamed all columns to `snake_case`.
- **Feature engineering:**
  - `age_group`: customer ages binned into groups
  - `purchase_frequency_days`: numeric version of purchase frequency
- **Data consistency check:** found `discount_applied` and `promo_code_used` redundant, so `promo_code_used` was dropped.
- **Database integration:** connected Python to PostgreSQL and loaded the cleaned DataFrame for SQL analysis.

### 2. SQL analysis (PostgreSQL)

Ten business questions were answered with SQL (see below).

### 3. Dashboard (Power BI)

An interactive dashboard was built to present the results visually.

## SQL Business Questions

| # | Question | Result |
|---|---|---|
| 1 | Revenue by gender | Male: $157,890, Female: $75,191 |
| 2 | High-spending discount users (discount used, spend above average) | 839 customers |
| 3 | Top 5 products by average rating | Gloves (3.86), Sandals (3.84), Boots (3.82), Hat (3.80), Skirt (3.78) |
| 4 | Average purchase by shipping type | Express: $60.48, Standard: $58.46 |
| 5 | Subscribers vs. non-subscribers | Subscribers: 1,053 customers, $59.49 avg spend, $62,645 revenue. Non-subscribers: 2,847 customers, $59.87 avg spend, $170,436 revenue |
| 6 | Top 5 discount-dependent products | Hat (50.00%), Sneakers (49.66%), Coat (49.07%), Sweater (48.17%), Pants (47.37%) |
| 7 | Customer segmentation | Loyal: 3,116, Returning: 701, New: 83 |
| 8 | Top 3 products per category | e.g. Accessories: Jewelry, Sunglasses, Belt. Clothing: Blouse, Pants, Shirt |
| 9 | Repeat buyers (more than 5 purchases) and subscriptions | Non-subscribed: 2,518, Subscribed: 958 |
| 10 | Revenue by age group | Young Adult $62,143, Middle-aged $59,197, Adult $55,978, Senior $55,763 |

## Key Findings

- **Male customers generate roughly twice the revenue** of female customers ($157,890 vs. $75,191).
- **Only 27% of customers subscribe**, and subscribers spend about the same per purchase as non-subscribers ($59.49 vs. $59.87).
- **The customer base is mostly loyal:** 3,116 of 3,900 customers fall in the Loyal segment.
- **Most repeat buyers are not subscribed** (2,518 vs. 958), which points to a conversion opportunity.
- **Express shipping users spend slightly more** per purchase than Standard users.
- **Hat is both top rated and the most discount-dependent** product (50% of its purchases are discounted).
- **Young Adults are the top revenue age group**, but all groups are within a narrow range.

## Power BI Dashboard

The **Customer Behavior Dashboard** shows:

- KPIs: number of customers (3.9K), average purchase amount ($59.76), average review rating (3.75)
- Share of customers by subscription status (Yes 27%, No 73%)
- Revenue and sales by product category
- Revenue and sales by age group
- Slicers for subscription status, gender, category and shipping type

> Add a screenshot here, e.g. `![Dashboard](images/dashboard.png)`

## Business Recommendations

1. **Boost subscriptions:** promote exclusive benefits for subscribers.
2. **Customer loyalty programs:** reward repeat buyers to move them into the Loyal segment.
3. **Review discount policy:** balance sales boosts with margin control.
4. **Product positioning:** highlight top-rated and best-selling products in campaigns.
5. **Targeted marketing:** focus on high-revenue age groups and express-shipping users.

## Project Structure

Adjust this to match your repository.

```
├── data/
│   └── customer_shopping_behavior.csv
├── notebooks/
│   └── eda_and_cleaning.ipynb
├── sql/
│   └── business_queries.sql
├── dashboard/
│   └── customer_behavior_dashboard.pbix
├── images/
│   └── dashboard.png
├── reports/
│   └── Customer_Shopping_Behavior_Analysis.pdf
└── README.md
```

## How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/<your-username>/<your-repo>.git
   cd <your-repo>
   ```
2. **Install dependencies**
   ```bash
   pip install pandas numpy sqlalchemy psycopg2-binary jupyter
   ```
3. **Run the notebook** in `notebooks/` to clean the data and load it into PostgreSQL. Update the database connection details (user, password, host, database name) first.
4. **Run the SQL queries** in `sql/business_queries.sql` using pgAdmin, DBeaver or `psql`.
5. **Open the dashboard** file in Power BI Desktop and point it to your PostgreSQL database or the cleaned CSV.

## Author

**Your Name**
[LinkedIn](https://linkedin.com/in/your-profile) | [GitHub](https://github.com/your-username)
