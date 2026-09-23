# 📊 Sales Analytics Dashboard

A comprehensive data analytics project built with **Python** and **Streamlit** that analyses sales transactions from 2022 to 2025 across 6 countries, 4 sales channels, and multiple product categories.

---

## 📁 Project Structure

```
├── sales_analysis.py              # Streamlit frontend (main app)
├── sales_analysis.ipynb           # Jupyter Notebook (step-by-step analysis)
├── requirements.txt               # Python dependencies
├── Sales_transactions_2022_2025.csv  # Dataset (18,045 transactions)
├── README.md                      # This file
└── Sales_Analysis_Report.docx     # Full project report
```

---

## 📦 Dataset Overview

| Property         | Value                              |
|------------------|------------------------------------|
| File             | `Sales_transactions_2022_2025.csv`(https://www.kaggle.com/datasets/danielsowah123/retail-sales-dataset?resource=download) |
| Rows             | 18,045 transactions                |
| Columns          | 32                                 |
| Years            | 2022, 2023, 2024, 2025             |
| Countries        | USA, Australia, France, Canada, UK, Germany |
| Sales Channels   | Online, Retail Store, B2B Portal, Phone Order |
| Product Categories | Electronics, Office Supplies, Furniture, Appliances |

---

## 🚀 Getting Started

### 1. Clone or download the project

```bash
git clone <your-repo-url>
cd sales-analytics
```

### 2. Create a virtual environment (recommended)

```bash
python -m venv venv
# Windows
venv\Scripts\activate
# macOS / Linux
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Streamlit app

```bash
streamlit run sales_analysis.py
```

The app will open in your browser at `http://localhost:8501`.

### 5. (Optional) Run the Jupyter Notebook

```bash
jupyter notebook sales_analysis.ipynb
```

---

## 📋 Analysis Steps

### Step 1 — Load Data
Reads the CSV file using `pandas.read_csv()` and inspects shape, dtypes, and sample rows.

### Step 2 — Data Quality Check
- Identifies missing values per column (10 columns had nulls).
- Standardises case inconsistencies in `Order_Status`, `Product_Category`, and other text columns.
- Fills missing numeric values with column **medians**.
- Fills missing text values with contextual defaults (`N/A`, `Unknown`, `None`).
- Parses `Order_Date` and derives `Order_Month`, `Order_Month_Name`, and `Order_Quarter`.

### Step 3 — Compute Total Sales
```python
df['Total_Sales'] = df['Quantity'] * df['Unit_Price']
```

### Step 4 — Group & Summarise
Aggregations (sum, count, mean) across:
- Year
- Product Category & Subcategory
- Country
- Sales Channel
- Customer Segment
- Monthly / Quarterly trends

### Step 5 — Charts
10+ charts including:
- Annual revenue bar chart
- Revenue by category (horizontal bar)
- Country revenue comparison
- Sales channel pie chart
- Monthly revenue trend lines (all 4 years)
- Top 15 products
- Customer segment revenue
- Order status distribution
- Return rate by category
- Grouped bar — category vs country

### Step 6 — Business Decisions
Data-driven recommendations on:
- Market investment priorities
- Category focus & stock strategy
- Channel UX improvements
- Seasonal campaign planning
- Returns reduction
- Promotions ROI
- Customer rating improvement

---

## 🖥️ Streamlit App Tabs

| Tab | Content |
|-----|---------|
| 🏠 Overview | KPI cards, annual revenue, category share |
| 🧹 Data Quality | Missing values, cleaning steps, cleaned dataset |
| 📦 Product Analysis | Category/subcategory revenue, top 15 products |
| 🌍 Regional Analysis | Country revenue, channel share, category×country |
| 👤 Customer Insights | Segments, age distribution, payment methods, return rates |
| 📅 Time Trends | Monthly trends, quarterly revenue, YoY growth |
| 💡 Business Decisions | 8 data-driven strategic recommendations |

All tabs respond to the **sidebar filters**: Year, Country, Product Category, Sales Channel, and Order Status.

---

## 🛠️ Tech Stack

| Library | Purpose |
|---------|---------|
| `pandas` | Data loading, cleaning, grouping |
| `matplotlib` | All charts |
| `seaborn` | Plot theming |
| `numpy` | Numerical operations |
| `streamlit` | Interactive web dashboard |

---

## 💡 Key Findings

- **United States** is the highest-revenue market.
- **Electronics** leads all product categories in total revenue.
- **Online** is the dominant sales channel.
- **Consumer** segment generates the most revenue.
- Promotions drive a measurable lift in average order value.
- Return rates vary by category — actionable for QC improvements.

---

## 📄 License

This project is for educational and analytical purposes.
