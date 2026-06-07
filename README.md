# 📊 Sales Performance Dashboard — Power BI

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

---

## 📌 Project Overview

An end-to-end interactive **Sales Performance Dashboard** built in Power BI, analyzing **2,000+ retail transactions** across **2 years (2023–2024)**. This project covers the full data pipeline — from raw CSV ingestion and automated cleaning in Power Query, to DAX-based KPI calculations and a fully interactive report with dynamic slicers and drill-down capabilities.

> Built as part of a data analyst portfolio to demonstrate real-world Business Intelligence skills.

---

## 🖼️ Dashboard Preview

![Dashboard Preview](dashboard_preview.png)

---

## 🎯 Business Questions Answered

- Which region generates the highest revenue and profit?
- Which products are the top 5 revenue drivers?
- How does revenue compare between 2023 and 2024 (YoY)?
- Who are the top performing salespersons?
- What is the overall profit margin and discount rate?
- How does revenue trend across months and seasons?

---

## ⚡ Key Features

| Feature | Details |
|---|---|
| 📈 KPI Cards | 8 live metrics — Revenue, Profit, YoY Growth, Margin, Orders, AOV, Units Sold, Discount Rate |
| 🔁 Dynamic Slicers | Filter entire dashboard by Year, Region, Date Range, Category |
| 🗺️ Regional Drill-down | Compare North, South, East, West performance side by side |
| 📦 Product Analysis | Top 5 revenue-driving products with automatic Top N filter |
| 👥 Salesperson Table | Individual performance breakdown with data bars |
| 📅 Time Intelligence | YoY comparison using SAMEPERIODLASTYEAR() DAX function |
| ⚙️ Automated Pipeline | Power Query M-language pipeline — auto-cleans on every refresh |

---

## 🧮 DAX Measures

```dax
Total Revenue = SUM(sales_data[Revenue])

Total Profit = SUM(sales_data[Profit])

Profit Margin % = DIVIDE([Total Profit], [Total Revenue])

Total Orders = COUNTROWS(sales_data)

Avg Order Value = DIVIDE([Total Revenue], [Total Orders])

Units Sold = SUM(sales_data[Quantity])

Avg Discount Rate = AVERAGE(sales_data[Discount])

YoY Revenue Growth =
VAR CY = [Total Revenue]
VAR PY = CALCULATE([Total Revenue],
    SAMEPERIODLASTYEAR('sales_data'[Date]))
RETURN DIVIDE(CY - PY, PY)
```

---

## 🔧 Power Query Steps

The raw CSV data was transformed through an automated pipeline:

1. **Source** — Loaded `sales_data.csv`
2. **Promoted Headers** — First row set as column headers
3. **Changed Types** — Date, Decimal, Integer types applied
4. **Inserted Year** — Extracted Year from Date column
5. **Inserted Month Name** — Extracted Month Name for timeline axis
6. **Inserted Month Number** — For correct chronological sorting

> Every step is recorded in M-language and re-runs automatically on data refresh — eliminating manual effort on future updates.

---

## 📊 Dataset Details

| Property | Value |
|---|---|
| Total Records | 2,000 rows |
| Time Period | January 2023 — December 2024 |
| Regions | North, South, East, West |
| Products | 10 products across 3 categories |
| Salespersons | 8 team members |
| Columns | OrderID, Date, Product, Category, Region, Salesperson, Quantity, UnitPrice, Discount, Revenue, Cost, Profit |

---

## 🛠️ Tools & Technologies

- **Power BI Desktop** — Report building and visualizations
- **DAX (Data Analysis Expressions)** — KPI measure calculations
- **Power Query (M Language)** — Data cleaning and transformation pipeline
- **Python (Pandas, NumPy)** — Sample dataset generation
- **Git & GitHub** — Version control and portfolio hosting

---

## 📁 Repository Structure

```
Sales-Performance-Dashboard-PowerBI/
│
├── 📊 SalesPerformanceDashboard.pbix   ← Main Power BI file
├── 📄 sales_data.csv                   ← Dataset (2000 rows)
├── 🖼️ dashboard_preview.png            ← Dashboard screenshot
└── 📝 README.md                        ← This file
```

---

## 🚀 How to Open This Project

1. Download and install **Power BI Desktop** (free) from [microsoft.com/power-bi](https://powerbi.microsoft.com/desktop)
2. Clone or download this repository
3. Open `SalesPerformanceDashboard.pbix` in Power BI Desktop
4. All data is embedded — dashboard loads immediately
5. Use the slicers on the right to explore the data interactively

---

## 💡 Key Insights from the Data

- **Electronics** dominates revenue at **76.87%** of total sales
- **Laptop Pro X1** is the single highest revenue-driving product
- **East region** leads all 4 territories in total revenue
- **YoY Growth of 92%** indicates strong business expansion in 2024
- **Profit Margin of 42%** is healthy across all categories

---

## 👤 Author

**Sharook Ahmed**
🎓 B.Tech — Artificial Intelligence & Data Science
🏫 St. Xavier's Catholic College of Engineering, Nagercoil

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat&logo=linkedin)](https://linkedin.com/in/sharookahmedm)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=flat&logo=github)](https://github.com/Sharooq-04)

---

## 📜 License

This project is open source and available under the [MIT License](LICENSE).

---

⭐ **If you found this project helpful, please give it a star!**
