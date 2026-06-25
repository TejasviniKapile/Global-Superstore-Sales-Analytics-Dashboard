# 🌐 Global Superstore Sales Analytics Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-green?style=for-the-badge)

## 📌 Project Overview
An industry-level interactive Power BI dashboard 
analyzing 51,290+ retail transactions across 
7 global markets from 2011 to 2014.
Built as a portfolio project for Data Analyst 
job applications.

---

## 🎯 Business Problem
GlobalMart Inc. needed a unified view of global 
sales performance to answer:
- Which markets and categories drive most profit?
- How does discounting impact margins?
- What are YoY growth trends?
- Which products are top performers?

---

## 📊 Dashboard Features
| Visual | Description |
|---|---|
| KPI Cards | Sales, Profit, Orders, Margin, AOV |
| Monthly Trend | Line chart with YoY comparison |
| Sales by Market | 7 global markets comparison |
| Profit by Category | Technology vs Furniture vs Office |
| Sales by Segment | Consumer, Corporate, Home Office |
| Top 10 Products | Ranked by Sales with Profit |
| Slicers | Year, Category, Market, Segment |

---

## 🛠️ Tools and Technologies
- **Tool:** Microsoft Power BI Desktop
- **Data Cleaning:** Power Query (M Language)
- **Calculations:** DAX
- **Data Source:** Global Superstore Dataset (Kaggle)
- **Dataset Size:** 51,290 rows × 25 columns

---

## 📐 Data Model
- Architecture: Star Schema
- DateTable created using CALENDAR() DAX function
- Relationship: DateTable[Date] → superstore[Order Date]
- Cardinality: One to Many (1:*)

---

## 🧮 DAX Measures Created
```dax
Total Sales = SUM(superstore[Sales])
Total Profit = SUM(superstore[Profit])
Total Orders = DISTINCTCOUNT(superstore[Order ID])
Profit Margin % = DIVIDE([Total Profit],[Total Sales],0)
Avg Order Value = DIVIDE([Total Sales],[Total Orders],0)
YTD Sales = TOTALYTD([Total Sales],DateTable[Date])
PY Sales = CALCULATE([Total Sales],SAMEPERIODLASTYEAR(DateTable[Date]))
Sales Growth % = DIVIDE([Total Sales]-[PY Sales],[PY Sales],0)
```

---

## 💡 Key Business Insights
1. **APAC is #1 market** by revenue
2. **Technology** has highest profit margin (~14%)
3. **Furniture** has lowest/negative margins
4. **Q4** shows consistent seasonal sales spike
5. **Consumer segment** = 51% of all orders
6. **High discounts (>40%)** always result in losses
7. **Standard Class** shipping used in 70%+ orders

---

## 📁 Repository Structure
