# Mercado-Livre-E-Commerce-Analytics
##  **📌 Overview**

This project analyzes Mercado Livre's e-commerce data (Brazil’s largest online marketplace) to uncover growth opportunities, optimize operations, and forecast sales trends. Leveraging SQL for data extraction, Power BI for visualization, and Python for predictive modeling, it delivers actionable insights into:

- Revenue volatility and seasonal trends

- Customer retention gaps (only 3.12% repeat buyers)

- Logistics inefficiencies (4.41% on-time deliveries)

- High-potential product categories (120K% YoY growth)

🔗 Dataset: Download Here

## **🛠️ Tools & Technologies** 

- **SQL** (MySQL): Data extraction and aggregation.

- Power BI: Interactive dashboards for stakeholder reporting.

- Python (Pandas, Scikit-learn, Statsmodels): EDA, time-series forecasting (Holt-Winters, Linear Regression).

- Jupyter Notebooks: Code documentation and analysis.

## **📂 Project Structure**  
```bash
├── SQL_Queries/               # 12 Advanced SQL queries (e.g., MoM growth, CLTV)
├── PowerBI_Dashboards/        # PBIX files & screenshots (6 thematic pages)
├── Python_EDA_Forecasting/    # Jupyter notebooks for:
│   ├── 1_Data_Cleaning.ipynb  
│   ├── 2_Revenue_Forecasting.ipynb  
│   └── 3_Category_Analysis.ipynb  
├── Reports/                   # Key insights and recommendations (PDF/PPT)
└── Resources/                 # Raw data, schemas, and helper scripts

```
## 🔍 Key Insights

1. **Revenue Trends**

	- Extreme MoM volatility (e.g., 699K% growth in Jan 2017).

	- Top categories (bed/bath, electronics) drove 35% of total revenue.

2. **Customer Behavior**

	- Avg. 80 days between 1st and 2nd purchase.

	- Debit card users gave highest ratings (4.17/5).

3. **Operational Gaps**

	- Northern states had 30-day delivery delays (vs. national avg: 12.5 days).

	- Sellers delivered 66 days earlier than estimated (algorithm recalibration needed).

4. **Forecasting**

	- Holt-Winters model outperformed Linear Regression (MAE: 255K vs. 845K).

## 🚀 How to Reproduce
1. **SQL Setup:**

```sql
-- Example: Monthly Revenue Growth Query
WITH monthly_revenue AS (...)
SELECT revenue_month, total_revenue, 
       (total_revenue - LAG(total_revenue) OVER (ORDER BY revenue_month)) / 
       NULLIF(LAG(total_revenue) OVER (ORDER BY revenue_month), 0) * 100 AS growth_pct
FROM monthly_revenue;

```
2. **Power BI:**  Import processed data and customize dashboards.

3. **Python:**  Install dependencies via requirements.txt and run notebooks.


## 📈 Deliverables

[12 SQL Queries (View Samples)](./sql%20query/mercado%20livre%20capstone%20project.sql)

[Power BI Dashboard (Screenshots)](./Power%20BI)

[Forecasting Models (Code)](./Python%20analysis/capestone%20.ipynb)

[Strategic Recommendations (PDF)](./actionable.pdf)

## 💡 Lessons Learned

Data Challenges: Handling date formats in SQL-Python integration.

Model Selection: Exponential Smoothing beat Linear Regression for seasonal data.

Stakeholder Focus: Dashboards prioritized KPIs like repeat purchase rate and delivery efficiency.

## 🌟 Showcase:

Adapt this for LinkedIn/portfolio with a focus on business impact (e.g., "Identified R$1.19M revenue opportunity in top categories").

MIT License

Copyright (c) 2025 Sagarkumar49

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

curl -o LICENSE https://raw.githubusercontent.com/github/choosealicense.com/main/_licenses/mit.txt
