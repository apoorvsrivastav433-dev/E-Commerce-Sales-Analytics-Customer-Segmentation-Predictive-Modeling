intern id -  cis401
 
 
 
 E-Commerce Sales Analytics, Customer Segmentation & Predictive Modeling

An end-to-end data analytics and machine learning portfolio project built on multi-table e-commerce transaction data (`orders.csv`, `customers.csv`, `products.csv`, and `payments.csv`). The project covers automated data cleaning, relational joins, feature engineering, exploratory visualizations, and predictive customer tier classification.

## Project Highlights

- **Data Cleaning & Relational Modeling:** Deduplicated `OrderID` records (`50,120` raw rows → `49,830` cleaned records), removed invalid quantities and missing dates, clipped discount bounds (`0.0` to `1.0`), imputed missing payment methods and demographics, normalized city names (`tehran` → `Tehran`, `Mashad` → `Mashhad`), and merged all tables into a unified analytical dataset.
- **Exploratory Analysis & Visualizations:** Tracked monthly realized revenue (`$3,207,099.40` across `45,839` completed orders), order fulfillment vs. cancellation/return rates (`8.01%` cancelled/returned), category performance, and top metropolitan markets.
- **Predictive Modeling:** Engineered customer-level behavioral features (`OrderCount`, `AvgQuantity`, `TenureDays`, `UniqueCategories`, `AvgDiscount`, `Age`) and benchmarked **Logistic Regression**, **Random Forest**, and **Gradient Boosting** classifiers to predict Top-Quartile High-Value Customers (**83.8% ROC-AUC**).

## Key Findings

1. **Realized Revenue & Fulfillment:** Completed orders generated **$3,207,099.40** in realized revenue, with an **8.01%** combined cancellation and return rate across raw order logs.
2. **Category Concentration:** **Electronics** is the top revenue driver at **$1,623.8K** (`50.6%` of realized revenue), ahead of **Accessories** (`$517.1K`) and **Home Office** (`$416.3K`).
3. **Top Geographic Markets:** **Tehran** leads all cities with **$879.6K** in realized revenue, followed by **Mashhad** (`$404.0K`) and **Karaj** (`$320.8K`).
4. **High-Value Buyer Drivers:** Feature importance from the Gradient Boosting classifier indicates that **Order Frequency (`49.8%`)** and **Average Basket Quantity (`25.1%`)** are the primary indicators of high-value customer spend.

## Visual Outputs

### 1. Monthly Realized Revenue & Completed Order Volume
![Monthly Revenue Trend](images/01_monthly_revenue_trend.png)

### 2. Realized Revenue by Product Category & Top 8 Cities
![Category and City Breakdown](images/02_category_city_breakdown.png)

### 3. Predictive Model Comparison & Feature Importance
![Predictive Model Performance](images/03_predictive_model_performance.png)

## Repository Structure

```text
ecommerce-sales-customer-intelligence/
├── data/
│   ├── raw/
│   │   ├── orders.csv
│   │   ├── customers.csv
│   │   ├── products.csv
│   │   └── payments.csv
│   └── processed/
│       └── clean_final_data.csv
├── notebooks/
│   └── 01_ecommerce_analysis_and_ml.ipynb
├── src/
│   └── data_pipeline.py
├── images/
│   ├── 01_monthly_revenue_trend.png
│   ├── 02_category_city_breakdown.png
│   └── 03_predictive_model_performance.png
├── requirements.txt
└── README.md
```

## Getting Started

### 1. Install Dependencies
```bash
pip install -r requirements.txt
```

### 2. Run the Pipeline or Notebook
- **Google Colab / Jupyter Notebook:** Open and run `notebooks/01_ecommerce_analysis_and_ml.ipynb` cell by cell.
- **Python Script:** Run `python src/data_pipeline.py` from the project root directory to generate the cleaned dataset and output charts.
