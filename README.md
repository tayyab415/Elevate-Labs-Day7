# Elevate-Labs-Day7

# Sales Summary with SQLite & Python

## Task 7: Get Basic Sales Summary from a Tiny SQLite Database using Python

This project demonstrates how to extract and visualize basic sales data (like total quantity sold and total revenue) from a small SQLite database using SQL in Python. The results are printed and plotted using `matplotlib`.

---

## Table of Contents

- `code.ipynb` – Python notebook for SQL query, data loading, and plotting
- `sales.db` – SQLite database file containing the sales table
- `sales_chart.png` – Saved bar chart showing revenue per product

---

## Tools Used

- Python (`sqlite3`, `pandas`, `matplotlib`)
- SQLite (built-in with Python)
- Jupyter Notebook

---

## Dataset

A small SQLite database (`sales.db`) with a single table storing product, quantity, and price details.

---

## How It Works

### 1. Connect to the Database

```python
import sqlite3
conn = sqlite3.connect("sales.db")
```

### 2. Run SQL Query

```sql
SELECT product,
       SUM(quantity) AS total_qty,
       SUM(quantity * price) AS revenue
FROM sales
GROUP BY product;
```

### 3. Load Data into Pandas

```python
import pandas as pd
df = pd.read_sql_query(query, conn)
```

### 4. Print the Results

```python
print(df)
```

### 5. Plot Bar Chart

```python
import matplotlib.pyplot as plt
df.plot(kind='bar', x='product', y='revenue')
```

### 6. Save the Chart (Optional)

```python
plt.savefig("sales_chart.png")
```

---

## Learning Outcomes

By completing this task, you will:

- Learn how to write basic SQL queries
- Practice importing SQL data into Python
- Perform simple data aggregation
- Create and save a basic bar chart using `matplotlib`
