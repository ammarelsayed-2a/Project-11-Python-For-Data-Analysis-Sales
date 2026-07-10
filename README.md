# Project-11-Python-For-Data-Analysis-Sales
End-to-end Sales Data Analysis on 254 transactions across 5 European cities (Nov-Dec 2022) | Data cleaning, revenue engineering &amp; business insights using Python, Pandas, Matplotlib &amp; Seaborn

# 💰 Sales Data Analysis — Fast Food Chain (Nov–Dec 2022)

An end-to-end Sales Data Analysis project on 254 transactions across 5 European cities, completed as part of the **Python for Data Analysis** course.

## 📌 Objective
Clean messy sales data, engineer a Revenue column, and answer 10 real business questions about payment preferences, top products, city performance, and revenue trends.

## 📂 Dataset
- **Source:** SalesData.xlsx
- **Records:** 254 transactions
- **Period:** November–December 2022
- **Cities:** London, Madrid, Lisbon, Berlin, Paris
- **Features:** Order ID, Date, Product, Price, Quantity, Purchase Type, Payment Method, Manager, City

## 🛠️ Tools & Libraries
| Library | Purpose |
|---|---|
| Pandas | Data cleaning, groupby, aggregation |
| Matplotlib | Bar charts, line charts |
| Seaborn | Statistical visualizations |

## 🔧 Pandas Commands Covered
| Command | Purpose |
|---|---|
| `str.strip().str.replace(r'\s+', ' ')` | Remove extra spaces in text columns |
| `drop_duplicates()` | Remove duplicate rows |
| `round()` | Round numerical values |
| `groupby().agg()` | Multiple aggregations in one call |
| `std()` / `var()` | Standard deviation and variance |
| `dt.month` | Extract month from datetime column |
| `resample('W')` | Aggregate by week |
| `sort_values(ascending=False)` | Sort descending |
| `reset_index()` | Convert Series index to DataFrame column |

## ⚠️ Key Data Cleaning Challenge
The `Manager` column had **14 "unique" values due to extra spaces** — when there are only 5 actual managers.  
`'Tom      Jackson'`, `'Tom Jackson'`, `'  Tom Jackson'` all referred to the same person.  
Without fixing this, every `groupby('Manager')` analysis would be completely wrong.

**Fix:**
```python
data['Manager'] = data['Manager'].str.strip().str.replace(r'\s+', ' ', regex=True)
```

## ❓ Analytical Questions

### Q1 — Most Preferred Payment Method
### Q2 — Most Selling Product (By Quantity & By Revenue)
### Q3 — City/Manager with Maximum Revenue
### Q4 — Date-wise Revenue
### Q5 — Average Revenue
### Q6 — Average Revenue of November & December
### Q7 — Standard Deviation of Revenue and Quantity
### Q8 — Variance of Revenue and Quantity
### Q9 — Was Revenue Increasing or Decreasing Over Time?
### Q10 — Average Quantity & Revenue for Each Product (using `agg()`)

## 📊 Analysis Structure
1. Imports & Setup
2. Load Dataset
3. First Look
4. Data Cleaning (Duplicates, Missing Values, Manager Fix, Revenue Column, Month Extraction)
5. Analytical Questions (Q1 → Q10)
6. Additional Visualizations
7. Key Insights

## 💡 Key Insights
- Cash is the most preferred payment method
- Burgers lead in revenue; Beverages lead in quantity sold
- Manager column had a critical data quality issue — 14 "unique" values were actually 5
- Revenue increased from November to December (holiday season effect)
- High revenue standard deviation suggests large variability in order sizes
- Paris generates the highest revenue among all cities

## 🚀 How to Run
```bash
git clone https://github.com/ammarelsayed-2a/Project-11-Python-For-Data-Analysis-Sales.git
cd Project-11-Python-For-Data-Analysis-Sales
jupyter notebook "Project 11 Sales.ipynb"
```

## 👤 Author
**Ammar Elsayed** — Python for Data Analysis | 2026  
[LinkedIn](https://www.linkedin.com/in/ammar-elsayed-ibrahim)
