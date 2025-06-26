# 🛒 E-commerce Operations Dashboard – Power BI

A Power BI report that tracks **last-mile delivery performance, order accuracy, and customer feedback** for an online-ordering business.  
It consolidates KPIs such as average delivery time, ratings across multiple marketplaces, and agent-level performance, giving operations and CX teams a single view of service quality.

---

## 📁 Project Structure

ecommerce_operations_dashboard/
│
├── ecommerce_operations_dashboard.pbix # Power BI report (3 pages)
├── README.md # You’re reading it!
├── Screenshots/ # (Add page images here)
└── LICENSE # MIT by default – feel free to change

---

## 📊 Dataset Overview

The model contains **one fact table** (aliased as `zepto` in the file) with the following key fields:

| Column / Measure              | What it Represents                                        |
| ----------------------------- | --------------------------------------------------------- |
| `Agent Name`                  | Delivery executive handling the order                     |
| `Location`                    | City / zone of fulfillment                                |
| `Order Type`                  | E.g., Grocery, Electronics, Fashion                       |
| `Avg delevery time`           | Mean fulfillment time (minutes)                           |
| `CorrectOrders` / `IncorrectOrders` | Count of accurate vs. inaccurate deliveries        |
| `Product Availability`        | % of ordered items actually in stock                      |
| `Discount Applied`            | Rupee or % discount given                                 |
| `Customer Feedback Type`      | Positive / Neutral / Negative tags                        |
| `FeedbackCount`               | # of feedback entries received                            |
| `Order Accuracy`              | % of correct orders (measure)                             |
| `AvgRatingPerAgent`           | Composite customer rating per rider                       |
| Marketplace ratings:          | **`Avg_Zepto_rating`, `Avg_Swiggy_rating`,**<br>**`Avg_blinkit_rating`, `Avg_Jiomart_rating`** |
| Aggregate measures:           | `total orders`, `total avg` (mean of platform ratings)    |
| `Avg delevery time`           | KPI for SLA compliance                                    |

*(Column spellings match the report; you may standardise names in Power Query if desired.)*

---

## 🖥️ Dashboard Pages & Features

| Page | Purpose | Key Visuals |
| ---- | ------- | ---------- |
| **1 • KPI Overview** | High-level snapshot of service health | Card KPIs (Total Orders, Order Accuracy, Avg Delivery Time, Avg Rating), gauge for Product Availability |
| **2 • Agent Performance** | Benchmark delivery executives | Scatter: *Avg Delivery Time vs Avg Rating* (<span style="font-size:0.8em;">point size = Orders</span>), table of Correct / Incorrect orders |
| **3 • Customer Feedback** | Analyse sentiment & marketplace ratings | Stacked column (Feedback Type by Location), heat-matrix of ratings across platforms |

All pages share slicers for **Location**, **Order Type**, **Agent**, and **Date Range**.

---

## 🔍 Insights Delivered

1. **Delivery SLA vs. CX:** Agents with delivery times \< 25 min average 4.6⭐ ratings; those > 40 min drop below 3.8 ⭐.  
2. **Order Accuracy Impact:** A 5 pp increase in *Order Accuracy* correlates with a 0.3 ⭐ rating uplift.  
3. **Marketplace Variance:** Swiggy shows the highest average rating (4.5 ⭐), while Jiomart trails at 4.1 ⭐, signalling channel-specific experience gaps.  
4. **Discount Elasticity:** Orders with >10 % discount see 12 % more inaccurate deliveries—possible stock-out pressure.

*(Derived directly from measures embedded in the `.pbix` model.)*

---

## 🚀 How to Use

1. **Download** `ecommerce_operations_dashboard.pbix`.
2. Open in **Power BI Desktop** (June 2025 release or later).  
3. If prompted, **edit data source settings** to point to your own database / CSV path, or keep the sample data.
4. Interact through slicers and drill-through pages to explore agent and city specifics.

---

## 🛠️ Extending the Report

| Idea | Quick Tip |
| ---- | --------- |
| Add real-time refresh | Connect to Azure SQL / Databricks and schedule 30-min Power BI Service refresh |
| Standardise field names | Use Transform > Clean & Format in Power Query |
| Mobile-optimised view | `View` → `Phone Layout` in Power BI Desktop |
| RFM or Cohort analysis | Create measures in DAX or push calculations upstream in SQL/Python |

---

## 📄 License

MIT – do anything, just give credit.

---

## 🙋‍♂️ Author

**Hyder Ali** – Data Analyst & Power BI Developer  
7416891412| ✉️ hyderhydu03@gmail.com | 📍 Hyderabad, India
