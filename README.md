# 🛒 Customer Shopping Behavior Analysis

> An end-to-end data analysis project covering data loading, exploratory data analysis, data cleaning, SQL querying, and Power BI dashboard development.

---

## 📌 Overview

This project analyzes customer shopping behavior data to uncover trends in purchasing patterns, product performance, and customer segmentation. The goal is to help a retail business make data-driven decisions around marketing, product strategy, and customer engagement.

The pipeline covers the full data analysis workflow — from raw data ingestion in Python to interactive visualization in Power BI — with SQL used for structured business queries on a MySQL server.

---

## 📂 Dataset

| Detail | Info |
|---|---|
| **Source** | [Kaggle – Customer Shopping Dataset](https://www.kaggle.com/) *(update with actual link)* |
| **Records** | 3,000+ rows |
| **Format** | CSV |
| **Key Columns** | Customer ID, Age, Gender, Product Category, Purchase Amount, Review Rating, Payment Method |

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **Python** | Data loading, EDA, data cleaning |
| **Pandas & NumPy** | Data manipulation and analysis |
| **Matplotlib & Seaborn** | Exploratory visualizations |
| **MySQL** | Structured querying and business logic |
| **MySQL Connector (Python)** | Connecting Python to MySQL server |
| **Power BI** | Interactive dashboard and final reporting |
| **Jupyter Notebook** | Development environment |

---

## 🔢 Project Steps

### 1. 📥 Data Loading
- Imported the CSV dataset using `pandas.read_csv()`
- Previewed structure with `.head()`, `.info()`, and `.describe()`
- Checked data types, column names, and row counts

### 2. 🔍 Exploratory Data Analysis (EDA)
- Analyzed distributions of key variables (age, purchase amount, ratings)
- Identified top-selling product categories and high-revenue customer segments
- Visualized patterns using bar charts, histograms, and correlation heatmaps

### 3. 🧹 Data Cleaning
- Handled missing values and removed duplicate rows
- Standardized inconsistent text values (e.g., category names, gender labels)
- Converted data types where needed (dates, numerics)
- Validated cleaned data before exporting

### 4. 🗄️ SQL Queries on MySQL Server
- Loaded cleaned data into a MySQL database
- Ran business-focused queries including:
  - Revenue analysis by gender
  - Top products by average review rating
  - Revenue contribution by age group
  - Purchase frequency by payment method

### 5. 📊 Power BI Dashboard
- Connected Power BI to MySQL server for live data
- Built an interactive dashboard with filters by gender, category, and age group
- Visualized KPIs: total revenue, average order value, top categories, customer segments

---

## 📊 Dashboard Preview

> 📎 *Add a screenshot of your Power BI dashboard here*

```
Insert dashboard screenshot:
![Dashboard Preview](dashboard/dashboard_preview.png)
```

**Key visuals included:**
- 💰 Total Revenue KPI Card
- 🛍️ Sales by Product Category (Bar Chart)
- 👥 Customer Segmentation by Age & Gender (Donut / Stacked Bar)
- ⭐ Product Performance by Review Rating (Table)
- 📈 Monthly Purchase Trend (Line Chart)

---

## 📈 Key Results & Insights
Gender revenue gap: Male customers generated ~157,890 in total revenue vs. ~75,191 from female customers — nearly double, indicating a significant gender skew in spend that could inform targeted marketing allocation.
Customer loyalty distribution: Using a CTE-based segmentation (New / Returning / Loyal by purchase history), ~80% of the customer base (3,116 of ~3,900 customers) falls into the "Loyal" tier, with only 83 New customers — suggesting strong retention but a potential gap in new customer acquisition.
Subscription status is not a proxy for loyalty: Average spend was nearly identical between subscribers (59.49) and non-subscribers (59.87). Even among repeat buyers (5+ previous purchases), non-subscribers outnumbered subscribers ~2.6:1 (2,518 vs. 958) — indicating the subscription program may be under-promoted relative to actual customer loyalty.
Top-rated products: Gloves, Sandals, Boots, Hat, and Handbag led average review ratings, all tightly clustered between 3.78–3.86 — no single runaway product, suggesting rating alone isn't a strong differentiator without pairing it with volume.
Discount usage: Hat (50%), Sneakers (49.7%), Coat (49.1%), Sweater (48.2%), and Pants (47.4%) had the highest share of discounted purchases — consistently high across varied product types, not isolated to one category.
Shipping type and spend: Average purchase amount was nearly identical between Express (60.48) and Standard (58.46) shipping — shipping preference showed little correlation with basket size.
Age group revenue: Fairly evenly distributed across Young-Adult (62,143), Middle-Aged (59,197), Adult (55,978), and Senior (55,763) — no single age group dominates, making age a weaker lever for targeting compared to gender or subscription behavior.
Top products by category: Identified top 3 best-selling products within each category (Accessories, Clothing, Footwear, Outerwear) using ROW_NUMBER() with PARTITION BY — noted that tied order counts were assigned distinct ranks due to ROW_NUMBER's behavior, a case where RANK()/DENSE_RANK() would better preserve ties

---

## ▶️ How to Run This Project

### Prerequisites
Make sure you have the following installed:
- Python 3.8+
- MySQL Server
- Power BI Desktop (free download from Microsoft)
- Jupyter Notebook

### Step 1 — Clone the Repository
```bash
git clone https://github.com/yourusername/customer-shopping-analysis.git
cd customer-shopping-analysis
```

### Step 2 — Install Python Dependencies
```bash
pip install pandas numpy matplotlib seaborn mysql-connector-python jupyter
```

### Step 3 — Run the Jupyter Notebook
```bash
jupyter notebook
```
Open `notebooks/eda_and_cleaning.ipynb` and run all cells.

### Step 4 — Set Up MySQL Database
```bash
mysql -u root -p
```
```sql
CREATE DATABASE shopping_db;
USE shopping_db;
SOURCE sql/create_tables.sql;
```
Then run the queries in `sql/business_queries.sql`.

### Step 5 — Open the Power BI Dashboard
- Open `dashboard/shopping_dashboard.pbix` in Power BI Desktop
- Update the MySQL connection string with your local credentials
- Refresh the data and explore the dashboard

---

## 📁 Project Structure

```
customer-shopping-analysis/
│
├── data/
│   ├── raw/                  # Original dataset
│   └── cleaned/              # Cleaned dataset (post-Python processing)
│
├── notebooks/
│   └── eda_and_cleaning.ipynb
│
├── sql/
│   ├── create_tables.sql
│   └── business_queries.sql
│
├── dashboard/
│   ├── shopping_dashboard.pbix
│   └── dashboard_preview.png
│
└── README.md
```

---

## 👩‍💻 Author

**Druthi D**
📧 druthidhananjaya60@gmail.com
🔗 [linkedin.com/in/druthidhananjaya](https://linkedin.com/in/druthidhananjaya)
🐙 [github.com/yourusername](https://github.com/yourusername)

---

*Feel free to fork this project, raise issues, or reach out if you have any questions!*
