# Target Data Analysis

## Project Overview
This project focuses on Exploratory Data Analysis (EDA) of Target retail data to understand customer behavior, sales patterns, and operational insights. The analysis helps identify trends, high-performing segments, and potential business opportunities.

---

## Tools & Technologies
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## Dataset Description
The dataset contains transactional and customer-related information from Target.

**Typical columns may include:**
- Order ID
- Customer ID
- Product Category
- Price / Sales
- Quantity
- Order Date
- Shipping Date
- Location / Region

> Column names may vary. Update the notebook code if needed.

---

## Installation

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

---

## How to Run the Project
1. Clone or download this repository.
2. Place the dataset CSV file in the project directory.
3. Open the notebook:
```bash
jupyter notebook "Target Data Analysis.ipynb"
```
4. Run the cells sequentially.

---

## Analysis Workflow

### Import Required Libraries
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

### Load Dataset
```python
df = pd.read_csv("target_data.csv")
df.head()
```

### Data Understanding & Cleaning
```python
df.info()
df.describe()
df.isnull().sum()
```

### Feature Engineering
```python
df['Order Date'] = pd.to_datetime(df['Order Date'])
df['Year'] = df['Order Date'].dt.year
df['Month'] = df['Order Date'].dt.month
```

### Sales Trend Analysis
```python
plt.figure(figsize=(12,5))
sns.lineplot(data=df, x='Order Date', y='Sales')
plt.title("Sales Trend Over Time")
plt.show()
```

### Category-wise Sales
```python
category_sales = df.groupby('Category')['Sales'].sum().sort_values(ascending=False)

plt.figure(figsize=(10,5))
sns.barplot(x=category_sales.values, y=category_sales.index)
plt.title("Sales by Product Category")
plt.show()
```

---

## Key Insights
- Sales show noticeable trends over time.
- Certain product categories dominate total revenue.
- Temporal features help identify peak sales periods.

---

## Conclusion
This analysis provides actionable insights into Target’s sales and customer patterns. The results can support decision-making in inventory management, marketing strategy, and demand forecasting.

---

## Future Improvements
- Customer segmentation using clustering
- Predictive sales forecasting
- State/region-wise performance analysis
- Interactive dashboards

---

## License
This project is released under the MIT License.
