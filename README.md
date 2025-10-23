<img width="1241" height="690" alt="image" src="https://github.com/user-attachments/assets/a231e525-8efd-4abf-aeec-f426ce55d41f" />

````markdown
# 🧭 Retail Sales Analysis – Power BI Project

##  Project Overview
This project demonstrates an **end-to-end data analytics and dashboarding process** using **Power BI, Excel, SQL, and Python** — focused on retail sales performance, profitability, and regional trends.

The dataset covers **3,000+ sales transactions across 2023–2024**, spanning multiple products, customers, cities, and channels.  
The dashboard delivers business insights around revenue, orders, profit, customer segmentation, and regional performance — designed for **data-driven decision-making**.

---

##  Business Objective
To analyze key sales and profit metrics that can:
- Track revenue growth and profitability trends over time  
- Identify top-performing product categories and regions  
- Evaluate customer segments and sales channels  
- Enable leadership teams to make faster, data-backed strategic decisions  

---

##  Data Model & Architecture
The project follows a **Star Schema** for clean and efficient analytics:

| Table | Description |
|-------|--------------|
| **FactSales** | Contains transactional details like OrderDate, Quantity, UnitPrice, Discount, ShippingCost |
| **DimProduct** | Includes ProductName, Category, Subcategory, Brand, and UnitCost |
| **DimCustomer** | Contains CustomerID, CustomerName, and Segment |
| **DimGeo** | Defines Country, Region, State, City, and coordinates for map visuals |
| **DimDate** | Holds temporal hierarchy like Year, Month, Quarter, and Week |

>  *All data is clean, with no missing values and consistent keys.*

---

##  Key Measures (DAX)
A few of the key calculated measures used:

```DAX
Total Revenue =
SUMX (
    FactSales,
    FactSales[Quantity] * FactSales[UnitPrice] * (1 - FactSales[Discount])
)

Total Orders = DISTINCTCOUNT(FactSales[OrderID])

AOV = DIVIDE([Total Revenue], [Total Orders])

Total Profit =
VAR COGS = SUMX(FactSales, FactSales[Quantity] * RELATED(DimProduct[UnitCost]))
VAR Shipping = SUM(FactSales[ShippingCost])
RETURN [Total Revenue] - COGS - Shipping
````

Additional measures include:

* **Revenue LY** (YoY comparison)
* **YoY % Growth** using SAMEPERIODLASTYEAR

---

##  Dashboard Highlights

The Power BI dashboard contains **9 visuals** arranged for clarity and decision support:

| Visual                     | Description                                        |
| -------------------------- | -------------------------------------------------- |
| **KPI Cards**              | Total Revenue, Profit, Orders, Customers, Quantity |
| **Line Chart**             | Revenue trend by Month                             |
| **Clustered Column Chart** | Revenue by Category                                |
| **Stacked Bar Chart**      | Revenue by Region and Channel                      |
| **Map Visual**             | City-level bubbles sized by Revenue                |
| **Matrix Table**           | Category vs Region (Revenue & Profit)              |
| **Donut Chart**            | Segment-wise Revenue Contribution                  |

Each visual is fully interactive with slicers for **Year, Category, and Channel** filters.

---

##  Insights Derived

1. **Technology** and **Office Supplies** categories contribute the highest revenue.
2. **North America** dominates in total sales, while **Asia** shows the strongest YoY growth.
3. **Direct and Online channels** generate 75% of overall sales.
4. **AOV (Average Order Value)** indicates strong cross-selling opportunities.
5. Profitability is maximized in **urban cities**, as revealed in the map visualization.

---

##  Tools & Technologies

* **Power BI** – Dashboard creation, DAX modeling, visual analytics
* **SQL (MySQL)** – Data cleaning, joins, aggregations, KPI extraction
* **Excel** – Exploratory analysis, pivot validation, and QA
* **Python (Pandas, NumPy, Matplotlib)** – Data preprocessing and trend analysis

---

## ⚙️ Workflow

1. Data cleaning and preprocessing in **Excel/Python**
2. Schema design and model creation in **Power BI**
3. DAX measures development for KPIs
4. Dashboard building and visual optimization
5. Validation through SQL queries and business checks

---

## About the Author

**Nikhil Kumar Mishra**
Senior Data Analyst | Growth & Strategy | Business Intelligence

Analytical and business-focused professional with experience across **growth analytics, data-driven decision support, and performance optimization** in fast-paced environments.
I’ve led analytics projects that improved operational efficiency and built BI dashboards tracking performance across multiple business verticals.

 I’m passionate about building **interactive dashboards** that don’t just display data — they tell stories and drive strategic actions.

📍 Noida, India
📧 [nikhilkumarmishra766@gmail.com](mailto:nikhilkumarmishra766@gmail.com)
🔗 [LinkedIn](https://www.linkedin.com/in/nikhil-kumar-mishra)
💻 [GitHub](https://github.com/nikhilkumarmishra)

---

##  Other Notable Projects

| Project                        | Tools                 | Description                                                 |
| ------------------------------ | --------------------- | ----------------------------------------------------------- |
| **Customer Churn Analysis**    | Python, SQL, Power BI | Predicted churn probabilities and visualized retention KPIs |
| **Supply Chain Data Analysis** | Power BI, SQL         | Improved supplier reliability and reduced cost variance     |
| **Sales Funnel Optimization**  | SQL, Power BI         | Analyzed conversion rates and marketing performance         |



##  Dashboard Preview

<img width="1916" height="1022" alt="image" src="https://github.com/user-attachments/assets/244c56ff-c609-487d-91a3-ec3f2633b1cb" />


---

