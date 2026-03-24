#  Ecommerce Delivery Performance Dashboard

A Power BI dashboard analyzing delivery performance, customer satisfaction, and operational efficiency across ecommerce platforms using a dataset of 1,00,000 orders.

---

##  Dashboard Preview

![Dashboard Preview](screenshots/dashboard_preview.png)

---

##  Project Objective

To analyze ecommerce delivery data and uncover insights about:
- Which platforms have the highest delivery delays
- Which product categories take the longest to deliver
- How delivery performance impacts customer ratings
- Overall on-time delivery rate and refund trends

---

##  Project Structure

```
ecommerce-delivery-dashboard/
│
├── data/
│   └── Ecommerce_Delivery_Analytics.csv
│
├── dashboard/
│   └── Ecommerce_Delivery_Dashboard.pbix
│
├── screenshots/
│   └── dashboard_preview.png
│
└── README.md
```

---

##  Dataset

| Field | Description |
|---|---|
| Order ID | Unique order identifier |
| Customer ID | Unique customer identifier |
| Platform | Delivery platform (JioMart, Blinkit, Swiggy Instamart) |
| Order Date & Time | Timestamp of order placement |
| Delivery Time (Minutes) | Total delivery duration |
| Product Category | Category of ordered product |
| Order Value (INR) | Order amount in Indian Rupees |
| Customer Feedback | Text feedback from customer |
| Service Rating | Rating given by customer (1–5) |
| Delivery Delay | Whether order was delayed (Yes/No) |
| Refund Requested | Whether refund was requested (Yes/No) |

- Total Records: **1,00,000 rows**

---

##  Dashboard Visuals

| Visual | Description |
|---|---|
| KPI Cards | Total Orders, Avg Delivery Time, Delay Rate %, On-Time Rate % |
| Delay Rate % by Product Category | Which categories face the most delays |
| Service Rating Distribution | Breakdown of customer ratings (1–5) |
| On-Time vs Delayed Orders | Donut chart showing delivery success rate |
| Platform Filter Slicer | Interactive filter by delivery platform |

---

##  DAX Measures Used

```dax
-- Average Delivery Time
Avg Delivery Time = AVERAGE('Ecommerce_Delivery_Analytics_Ne'[Delivery Time (Minutes)])

-- Delay Rate %
Delay Rate % = 
DIVIDE(
    COUNTROWS(FILTER('Ecommerce_Delivery_Analytics_Ne', 
        'Ecommerce_Delivery_Analytics_Ne'[Delivery Delay] = "Yes")),
    COUNTROWS('Ecommerce_Delivery_Analytics_Ne')
) * 100

-- On-Time Rate %
Ontime rate = 100 - [Delay Rate %]

-- Total Orders
Total Orders = COUNTROWS('Ecommerce_Delivery_Analytics_Ne')

-- Average Service Rating
Avg Service Rating = AVERAGE('Ecommerce_Delivery_Analytics_Ne'[Service Rating])

-- Refund Rate %
Refund Rate % = 
DIVIDE(
    COUNTROWS(FILTER('Ecommerce_Delivery_Analytics_Ne', 
        'Ecommerce_Delivery_Analytics_Ne'[Refund Requested] = "Yes")),
    COUNTROWS('Ecommerce_Delivery_Analytics_Ne')
) * 100
```

---

##  Key Insights

- Overall on-time delivery rate is **86.33%**
- Average delivery time across all platforms is **29.54 minutes**
- Overall delay rate stands at **13.67%**
- Blinkit has the highest delay rate at **13.38%**
- Majority of customers rated service **5 stars**, indicating high satisfaction

---

##  Tools Used

| Tool | Purpose |
|---|---|
| Power BI Desktop | Dashboard creation and DAX measures |
| CSV Dataset | Data source (1,00,000 rows) |
| GitHub | Version control and portfolio hosting |

---

##  Author

**Chandrakanth Reddy Bonthala**
-  [GitHub](https://github.com/ChandrakanthReddyBonthala)

---

##  Note

This project was built as part of my data analyst portfolio to demonstrate skills in Power BI, DAX, and data visualization.
