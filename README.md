# Ecommerce Order & Logistics Analysis — Power BI

A 4-page Power BI report analyzing e-commerce order data (Q1 FY2022-23 / Apr-Jun 2022) — covering financial performance, customer behavior, and logistics/inventory operations, with a dedicated conclusions page translating findings into business recommendations.

## 📊 Business Problem

E-commerce operations teams need visibility into where revenue is being generated, why orders are cancelled or returned, and how fulfillment is performing across sellers (Amazon vs. Merchant) and shipping methods — to guide pricing, inventory, and logistics decisions.

## 🖼️ Preview

### Financial Performance Analysis
![Financial Analysis](Financial%20Analysis.png)

### Customer Insights Analysis
![Customer Insights](Customer%20insight.png)

### Logistic & Inventory Analysis
![Logistic Inventory](Logistic%20Inventory.png)

### Conclusion & Recommendations
![Key Findings](Key%20Findings.png)

## ✅ Key Features

- **4-page report**: Financial Performance, Customer Insights, Logistic & Inventory, Conclusion & Recommendations
- Revenue breakdown by category, state, and month
- Cancellation and retention rate tracking with root-cause breakdowns (by state, category, month)
- B2B vs. B2C order split, Amazon vs. Merchant fulfillment comparison
- Size and SKU-level inventory analysis (Top 5 SKUs by revenue, order distribution by size)
- Dedicated insights page with data-driven recommendations

## 🗂️ Data Model

Star schema:
- **Sales fact** (Amount, ASIN, B2B, B2b-B2c, Courier Status, Date, Fulfilment, Location.State id)
- **Product** (Category, Size, SKU, Style)
- **Location** (ship-state, State_id)
- **DateTable** (Date, Month Name, Month Number, Years)

## 🧮 Key DAX Measures

```dax
Total Revenue = SUM('Sales fact'[Amount])

Cancellation Rate = DIVIDE([Cancelled order], [Total Orders])

Retention Rate = 1 - [Cancellation Rate]

Avg Orders Value = DIVIDE([Total Revenue], [Total Orders])
```

## 💡 Key Insights & Recommendations

**Financial**
- Total revenue: 71M (Apr-Jun 2022)
- Revenue trend declined from 26M to 21.3M across the quarter
- "Set" is the top-selling category (35.5M)
- Maharashtra is the highest-revenue state

**Customer**
- 99.34% of customers are B2C
- Cancellation rate: 9.98% · Retention rate: 90.02%
- Maharashtra also has the highest cancellation volume

**Logistics**
- Amazon fulfills 72.29% of orders; Merchant fulfills the remaining 27.71%
- 68.86% of orders use Expedited shipping
- 2K returns and 846 pending orders

**Inventory**
- M, L, and XL are the highest-demand sizes
- Set and Kurta together account for 78% of total quantity sold
- J0230-SKD-M is the top-revenue SKU

**Recommendations**
1. Investigate the quarter-over-quarter revenue decline
2. Reduce cancellation rate by analyzing high-cancellation states and categories
3. Grow the underdeveloped B2B segment
4. Reduce XS and 6XL stock levels given low demand
5. Improve Merchant fulfillment performance relative to Amazon

## 🛠️ Tools Used

Power BI · DAX · Power Query
