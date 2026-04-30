# 📦 Delivery Performance Analytics

End-to-end data analytics project demonstrating a full workflow from raw CSV files to validated Power BI dashboards using PostgreSQL and Python.

---

## 🧠 Project Overview

This project simulates a real-world analytics pipeline and focuses on **delivery performance analysis** using a relational dataset consisting of six connected tables.

The main goals of the project are:

- Build a clean and reliable analytical dataset
- Validate data quality and logical consistency
- Measure delivery efficiency and on-time performance
- Present clear, business-oriented insights

---

## 🗂 Data Sources

The project uses **six related CSV files**, representing a transactional e-commerce system:

- Order İtems
- Customers
- Order payments
- Order
- Product summarize
- reviews

These files were treated as raw input data and never modified directly.

---

## 🔁 Data Pipeline

### 1️⃣ Data Ingestion (CSV → PostgreSQL)

- All raw CSV files were imported into **PostgreSQL**
- A relational schema was created to validate relationships between tables
- PostgreSQL served as a centralized and structured storage layer

### 2️⃣ Data Cleaning & Transformation (Python)

- Data was accessed from PostgreSQL using **Python (psycopg2)**
- Exploratory analysis was performed using descriptive statistics
- Key cleaning and transformation steps:
  - Standardization of city and location names
  - Removal of irrelevant columns and records
  - Handling missing and blank values

### 3️⃣ Curated Dataset Creation

- Cleaned and transformed tables were exported as new CSV files
- Clear separation was maintained between **raw** and **processed** datasets
- This approach improves reproducibility and transparency

### 4️⃣ Data Modeling & Visualization (Power BI)

- Processed datasets were loaded into **Power BI**
- Additional transformations were applied where needed:
  - Converting numeric values stored as text (e.g. commas used as decimal separators)
  - Ensuring correct data types for dates and numeric fields
  - Validating table relationships
  - Detection of logically inconsistent records (e.g. delivery date earlier than approval date)

Invalid records were flagged and excluded from delivery time calculations to ensure data reliability.

---

## 📊 Key Metrics & Analysis


The dashboard focuses on a limited set of **high-impact KPIs**:

- Delivery success rate
- On-time vs late delivery distribution
- Average delivery duration for on-time / early deliveries

The number of visuals was intentionally limited to avoid visual noise and keep insights actionable.

---

## 📈 Key Insights
- Delivery delays spiked sharply in Jan–Mar 2018: +120.5% in February and +51.4% in March, peaking at 1,530 late deliveries
- February spike was driven by the **Computer Accessories** category showing disproportionately high delay rates
- March peak was linked to **Brazil's carnival season**, causing nationwide logistics overload — confirmed by uniform delay distribution across all regions (ruling out local supply chain issues)
- Regional and operational factors were ruled out: estimated delivery time remained stable at 30–37 days throughout the period
- After March 2018, late delivery counts declined consistently, suggesting the disruption was seasonal rather than structural

## 🛠 Tools & Technologies

- **PostgreSQL** – relational data storage and validation
- **Python** (`psycopg2`, `pandas`) – data cleaning and transformation
- **SQL** – schema creation and data validation
- **Power BI** – data modeling and visualization

---

## 📁 Repository Structure

```text
📦 delivery-performance-analytics
├── data
│   ├── raw
│   ├── processed
│   └── data_dictionary.md
├── sql
├── python
├── powerbi
├── analysis
└── README.md
```
---
## 📸 Dashboard Preview

![February Crisis](images/february.png)

![March Crisis](images/march_crisis.png)

![Dashboard Overview](images/second_page.png)
