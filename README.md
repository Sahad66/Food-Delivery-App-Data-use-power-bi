# 🍔 Food Delivery App Analytics Dashboard

An end-to-end **Power BI** project that analyzes 200K food delivery orders across restaurants, customers, cities and delivery performance to uncover revenue drivers, delivery bottlenecks and customer behavior.

---

## 📌 Project Overview

| | |
|---|---|
| **Domain** | Food Delivery / Restaurant Analytics |
| **Tool** | Power BI Desktop (PBIP project format) |
| **Data size** | 200,000 orders · 20,000 customers · ~56K restaurants |
| **Pages** | 6 (Executive Overview, Customer Analysis, Delivery, Restaurant Performance, Advanced Insights, Restaurant Details) |

### Business Questions Answered
- How much revenue and how many orders is the platform generating, and how is it trending?
- Who are the customers: new, returning or premium, and how loyal are they?
- How reliable is delivery? What share of orders are late or cancelled?
- Which cities, cuisines and restaurants drive the most revenue?
- Do rating and price range (cost bucket) influence revenue?

---

## 📊 Dashboard Preview

### 1. Executive Overview
<img width="1319" height="751" alt="Executive overview" src="https://github.com/user-attachments/assets/3ab15ea5-93bb-43e7-b9a3-f9814561f96f" />


### 2. Customer Analysis
![Customer Analysis](images/customer_analysis.png)

### 3. Delivery Performance
![Delivery Performance](images/delivery.png)

### 4. Restaurant Performance
![Restaurant Performance](images/restaurant_performance.png)

### 5. Advanced Insights
![Advanced Insights](images/advanced_insights.png)

### 6. Restaurant Details (Drill-through)
![Restaurant Details](images/restaurant_details.png)

---

## 🔑 Key KPIs

| KPI | Value |
|---|---|
| Total Revenue | **165M** |
| Total Orders | **200K** |
| Avg Order Value | **824.57** |
| Avg Delivery Time | **44.55 min** |
| Total Customers | **20K** |
| Repeat Customers % | **50.28%** |
| Orders per Customer | **10.00** |
| Late Delivery % | **48.12%** |
| Cancelled Orders | **~20K (9.97%)** |
| Total Restaurants | **56K** |
| Avg Rating | **3.70** |
| Revenue per Restaurant | **2.93K** |

---

## 🗂️ Dashboard Pages

| Page | What it shows |
|---|---|
| **Executive Overview** | Top-level KPIs, order status breakdown, revenue by city, top restaurants, revenue & order trends |
| **Customer Analysis** | New vs Repeat vs Premium customers, orders by customer type, sign-up trend, top restaurants by city |
| **Delivery Performance** | On-time vs late split, city-wise delivery time, cancellations by city, delivery status table |
| **Restaurant Performance** | Rating by cuisine, orders by cuisine, cost bucket distribution, top 10 restaurants by revenue, rating vs revenue |
| **Advanced Insights** | KPI switcher (Avg Delivery Time / Orders / Avg Order Value / Revenue), Revenue vs Rating vs Cost bubble chart, Q&A natural-language visual |
| **Restaurant Details** | Drill-through page with KPIs, delivery status, customer-type mix and revenue trend for a single restaurant |

---

## 💡 Key Insights

1. **Order fulfilment:** about **80%** of orders are delivered successfully, while roughly **10%** are delayed and **10%** cancelled.
2. **Delivery reliability is a concern:** **48.12%** of orders (≈96K) are marked late, with an average delivery time of **44.55 minutes**. City-level averages range up to about **55 minutes**.
3. **Customer loyalty:** about **50%** of customers are repeat customers, and each customer places around **10 orders** on average.
4. **Customer mix:** roughly **50% of orders come from new customers**, about **40% from returning customers** and **10% from premium customers**.
5. **Budget restaurants dominate demand:** Budget makes up **59%** of orders, Mid Range **28.5%** and Premium **12.4%**.
6. **Cuisine concentration:** the top cuisine alone accounts for about **44K orders**, more than double the next one (18K). Average rating across cuisines stays in a narrow **3.5–4.0** band.
7. **Revenue concentration:** revenue is spread thinly across many restaurants (avg **2.93K** per restaurant); the top restaurants reach **0.9M**.
8. **Rating vs revenue:** revenue peaks in the mid-to-high rating range, and Premium-priced restaurants earn most at higher ratings.
9. **Cancellations are city-skewed:** a few cities account for a disproportionately high number of cancelled orders (top city ≈ 1,876).

---

## 🎯 Recommendations

- Investigate late deliveries in the slowest cities and consider rider allocation or dispatch optimization there.
- Target cities with the highest cancellations with restaurant-side SLAs and customer communication.
- Launch loyalty offers to convert the large new-customer base into repeat customers.
- Promote high-rated restaurants in the mid-price segment, where rating and revenue align best.

---

## 🧮 Data Model & DAX

> Update this section to match your actual model.

**Model:** Star schema with an orders fact table connected to restaurant, customer, city and date dimensions.

**Sample measures:**

```DAX
Total Revenue      = SUM(Orders[Amount])
Total Orders       = COUNTROWS(Orders)
Avg Order Value    = DIVIDE([Total Revenue], [Total Orders])
Avg Delivery Time  = AVERAGE(Orders[DeliveryTime])
Late Delivery %    = DIVIDE(CALCULATE([Total Orders], Orders[DeliveryStatus] = "Late"), [Total Orders])
Cancelled Orders   = CALCULATE([Total Orders], Orders[OrderStatus] = "Cancelled")
Repeat Customer %  = DIVIDE([Repeat Customers], [Total Customers])
Orders per Customer = DIVIDE([Total Orders], [Total Customers])
```

---

## 🧹 Data Preparation (Power Query)

- Cleaned and standardized restaurant, city and cuisine fields
- Created `PrimaryCuisine`, `FilterCity` and `Cost Bucket` (Budget / Mid Range / Premium) columns
- Derived customer type (New / Returning / Premium) and delivery status (On Time / Late)
- Fixed data types and removed duplicates / nulls

---

## ✨ Power BI Features Used

- Drill-through page (Restaurant Details)
- KPI switcher for dynamic trend charts
- Bubble chart with three dimensions (Revenue × Rating × Cost Bucket)
- Conditional formatting in tables
- Q&A natural-language visual
- Consistent red / blue theme and card-based KPI layout

---

## 📁 Project Structure

```
├── Food Delivery App Data.pbip
├── Food Delivery App Data.Report/
├── Food Delivery App Data.SemanticModel/
├── data/
├── images/
│   ├── executive_overview.png
│   ├── customer_analysis.png
│   ├── delivery.png
│   ├── restaurant_performance.png
│   ├── advanced_insights.png
│   └── restaurant_details.png
└── README.md
```

---

## ▶️ How to Open

1. Install the latest **Power BI Desktop**.
2. Enable **Options → Preview features → Power BI Project (.pbip) save option**.
3. Open `Food Delivery App Data.pbip`.
4. If prompted, update the data source path to your local `data/` folder and refresh.

---

## 📥 Dataset

- Source: _[add dataset link / description here]_
- Period covered: _[add date range]_

---

## 👤 Author

**[Your Name]**
[LinkedIn](https://linkedin.com/in/your-profile) · [GitHub](https://github.com/your-username)
