# cafe-dashboard
# Power BI Sales Dashboard

## 📊 Overview

This project is a Power BI interactive dashboard built to analyze and visualize sales data, product performance, and ordering behavior over time.

Key insights include:
- Total Sales, Orders, and Quantity trends
- Product-wise sales and top-performing combos
- Daily, weekly, and monthly revenue breakdowns
- Dynamic metric switching (Sales/Orders/Quantity)
- KPI cards and growth comparisons (Week-over-week, Month-over-month)

---

## 🗃️ Dataset Description

The dataset includes customer order-level information and is organized around the following key fields:

| Column Name      | Description                                |
|------------------|--------------------------------------------|
| `order_id`       | Unique identifier for each order           |
| `created_at`     | Timestamp of the order                     |
| `product_id`     | ID of the product ordered                  |
| `product_name`   | Name of the product                        |
| `quantity`       | Quantity ordered                           |
| `total`          | Total sale amount for the line item        |
| `order_date`     | Date of the order (used for time analysis) |

---

## 📌 Features

- ✅ Dynamic metric selector using slicer (Sales / Orders / Quantity)
- ✅ KPI Cards for current and previous month metrics
- ✅ MoM & WoW growth visualizations
- ✅ Top product combo visual using DAX CONCATENATEX
- ✅ Responsive visuals using DAX measures and relationships
- ✅ Custom `DateTable` for flexible time intelligence

---

## 📁 Power BI Measures Used

- `Total Sales = SUM(order[total])`
- `Total Quantity = SUM(order[quantity])`
- `Total Orders = DISTINCTCOUNT(order[order_id])`
- `Previous Month Sales = CALCULATE([Total Sales], PARALLELPERIOD('DateTable'[Date], -1, MONTH))`
- `Dynamic Metric = SWITCH(...)`
- `Product Combo DAX`

---

## 🚀 How to Use

1. Clone the repo and open the `.pbix` file using Power BI Desktop
2. Interact with the slicer to switch between Sales, Orders, and Quantity
3. Use filters to narrow down by product or time period
4. Review KPIs and charts for insight

---

## 📌 Screenshots

| Weekly Revenue | Top Products |
|----------------|---------------|
| ![Weekly Revenue](screenshots/weekly_revenue.png) | ![Top Products](screenshots/top_products.png) |

---

## 📎 Requirements

- Power BI Desktop (latest version recommended)
- Sample dataset (imported CSV or database)

---

## 🧠 Notes

- Ensure the `DateTable` is marked as a **Date Table** in Power BI
- Relationships are set between `order[order_date]` and `DateTable[Date]`
- The metric selector is implemented using a disconnected table

---

## 📬 Contact

For any questions or feedback, please contact:

**Sharmili**  
📧 sharmili.ts@gantecusa.com
📦 GitHub: [imrahs](https://github.com/imrahs)

