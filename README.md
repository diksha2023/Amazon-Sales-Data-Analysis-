# Amazon Sales Data Analysis – Case Study

---

## Project Overview

### Objective
To analyze Amazon sales data to understand customer purchasing behavior, sales performance across categories and cities, payment method effectiveness, and factors influencing revenue, and to generate actionable business insights.

This project simulates a **real-world e-commerce analytics task**, similar to what a **Data Analyst or Data Scientist** would perform in a retail or marketplace company.

---

## Business Problem Statement

Amazon wants to answer the following business questions:

- Which **product categories** and **cities** generate the highest revenue?
- How do **payment methods** impact order value and order success?
- What factors drive higher **TotalAmount** (Quantity vs UnitPrice)?
- Are sales differences across product categories **statistically significant**?
- How can these insights help optimize **inventory, marketing, and operations**?

---

## Dataset Description

- **Rows:** 1000 orders  
- **Columns:** 10 original + engineered features  

### Key Columns

| Column | Description |
|------|-------------|
| OrderID | Unique order identifier |
| CustomerID | Unique customer identifier |
| ProductCategory | Category of product purchased |
| City | Customer city |
| Quantity | Number of items ordered |
| UnitPrice | Price per item |
| PaymentMethod | Mode of payment |
| OrderStatus | Delivered / Cancelled / Returned |
| OrderDate | Date & time of order |
| TotalAmount | Final order value |

---

## Data Cleaning & Preprocessing

### Steps Performed

- Checked missing values → **No nulls found**
- Converted categorical columns to `category` dtype
- Converted `OrderDate` to datetime format
- Extracted time-based features:
  - `OrderYear`
  - `OrderMonth`
  - `OrderDay`
  - `OrderHour`
- Optimized memory usage

**Result:** Clean, analysis-ready dataset

---

## Exploratory Data Analysis (EDA)

### 5.1 Univariate Analysis

**Key Findings:**

- Most orders have **Quantity between 2–3**
- Unit prices vary widely, indicating mixed product segments
- TotalAmount shows **right-skew**, meaning fewer but high-value orders exist

---

### 5.2 Categorical Analysis (Countplots)

**Insights:**

- **Books** are the most sold category  
- **Kolkata** has the highest number of orders  
- **Card payments** are most popular  
- ~**81% of orders are Delivered**

---

## Bivariate & Multivariate Analysis

### Product Category vs TotalAmount (Boxplots)

**Why boxplot?**  
ProductCategory is categorical and TotalAmount is numerical. Boxplots show:
- Median order value
- Spread
- Outliers (high-value orders)

**Insight:**
- Electronics & Home categories show **higher revenue variability**
- Books have more **consistent order values**

---

### Quantity vs TotalAmount (Scatter Plot)

**Why scatter plot?**  
Both variables are numerical → shows relationship strength.

**Insight:**
- Strong positive correlation
- Higher quantities → higher TotalAmount
- Quantity is a **major revenue driver**

---

### UnitPrice vs TotalAmount (Scatter Plot)

**Insight:**
- Even small quantities of high-priced items generate high revenue
- **UnitPrice influences TotalAmount more strongly than Quantity**

---

### City × ProductCategory Revenue (Grouped Analysis)

**Top combinations:**
- Home – Hyderabad  
- Sports – Delhi  
- Beauty – Kolkata  

These are **high-value micro-markets**

---

### Payment Method × Order Status × Revenue

**Insights:**
- Card & NetBanking have higher average order values
- COD shows lower success for high-value orders
- Returned orders tend to have higher ticket sizes

---

## Statistical Analysis

### Why Statistical Analysis is Important?

EDA shows patterns, but statistics tells us:
- Are these differences **real or random**?
- Can business decisions be **confidently justified**?

---

### 7.1 Correlation Analysis

- Quantity → TotalAmount: **Strong positive**
- UnitPrice → TotalAmount: **Very strong positive**

Revenue is driven more by **pricing strategy** than quantity.

---

### 7.2 Hypothesis Testing (t-test)

**Example:** Delivered vs Cancelled Orders  

- **p-value = 0.2267**
- p > 0.05 → No statistically significant difference

**Interpretation:**  
Order value alone does not strongly affect cancellations.

---

### 7.3 ANOVA Test (ProductCategory vs TotalAmount)

**Result:**  
ANOVA shows **significant variation** in TotalAmount across product categories.

**Interpretation:**  
Different product categories generate statistically different revenues.

---

### 7.4 Business Interpretation

- Category-based pricing strategies are justified
- Marketing budget should **not be equally distributed**

---

## Feature Engineering

### New Features Created

- `OrderHour`
- `OrderMonth`
- `AvgUnitPrice`
- `OrderSizeCategory` (Small / Medium / Large)
- `IsTopCustomer`

These features help in:
- Customer segmentation
- Time-based marketing
- Predictive modeling (future scope)

---

## Key Business Insights

### High-Impact Insights

- UnitPrice impacts revenue more than Quantity
- Electronics & Home categories drive premium revenue
- Certain city-category combinations outperform others
- Digital payments are safer for high-value orders
- Returns are often associated with expensive products

---

## Recommendations

### Focus Marketing On:
- High-value city-category pairs
- Digital payment incentives

### Optimize:
- Inventory planning for premium categories
- Return policies for high-value items

### Future Scope:
- Sales prediction model
- Customer lifetime value analysis
- Recommendation systems

---

## Tools & Skills Used

- Python (Pandas, NumPy)
- Matplotlib & Seaborn
- Statistical Testing (t-test, ANOVA)
- EDA & Feature Engineering
- Business Insight Generation

---

## Conclusion

This project demonstrates an **end-to-end data analysis workflow**, from raw data to business-ready insights.  
It reflects **real-world analytical thinking**, not just plotting graphs.
