# Data-Science-Devixo-Tasks
# Exploratory Data Analysis of a Sales Dataset

**Devixo Solutions - Data Science Internship Program | Task 01**
**Author:** Ateeb Mustapha

---

## Project Description

This project is a complete Exploratory Data Analysis (EDA) of a real-world sales dataset using Python. It follows the full workflow:

**Data Collection → Data Cleaning → Feature Analysis → Statistical Analysis → Visualization → Business Insights → Business Recommendations**

The goal is to find out what drives revenue, which categories, regions and sales reps perform well or poorly, whether discounts and quantities affect sales, and what practical actions a business could take based on the evidence.

---

## Dataset Information

- **Source:** Kaggle - (https://www.kaggle.com/datasets/vinothkannaece/sales-dataset)
- **File:** `sales_data.csv`
- **Size:** 1,000 records x 14 columns
- **Period covered:** January 2023 to early January 2024

| Column | Description |
|---|---|
| `Product_ID` | Product identifier (1001-1100) |
| `Sale_Date` | Date of the transaction |
| `Sales_Rep` | Alice, Bob, Charlie, David, Eve |
| `Region` | North, South, East, West |
| `Sales_Amount` | Revenue of the transaction |
| `Quantity_Sold` | Units sold |
| `Product_Category` | Clothing, Furniture, Electronics, Food |
| `Unit_Cost` | Cost per unit |
| `Unit_Price` | Selling price per unit |
| `Customer_Type` | New or Returning |
| `Discount` | Discount rate (0.00-0.30) |
| `Payment_Method` | Credit Card, Bank Transfer, Cash |
| `Sales_Channel` | Retail or Online |
| `Region_and_Sales_Rep` | Combined region and rep label |

---

## Technologies Used

- Python 3
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook / Google Colab
- Git and GitHub

---

## Analysis Performed

1. **Data import and understanding** - head/tail, shape, column names, data types, numerical vs categorical columns, basic statistics.
2. **Data cleaning** - missing values filled (median for numerical, mode for categorical), duplicates removed, dates converted to datetime, negative/invalid values checked, whitespace stripped, dataset verified and saved as `sales_data_cleaned.csv`.
3. **Feature analysis** - min, max, mean and median of numerical features, category frequencies, and outlier detection with the IQR method.
4. **Correlation analysis** - correlation matrix and heatmap, with strong, weak and important relationships identified.
5. **Data visualization** - 12 charts: histogram, bar chart, count plot, pie chart, scatter plot, line chart, box plot, violin plot, heatmap, pair plot, distribution plot and area chart.
6. **Business insights and recommendations** - 15 evidence-based insights and 7 recommendations tied directly to the results.

---

## Key Findings

- **Total revenue:** 5,019,265.23 from 1,000 transactions (25,355 units sold).
- **No revenue skew:** mean (5,019.27) and median (5,019.30) are almost identical, and the IQR method found **zero outliers** in every numerical column.
- **Top category:** Clothing (1,313,474.36, 26.2% of revenue). **Lowest:** Food (1,201,773.54, 23.9%), but Food has the **highest average sale** (5,317.58) and the fewest orders (226), so its weakness is order frequency, not order value.
- **Regions:** North leads (1,369,612.51, 27.3%), South is lowest (1,154,250.86, 23.0%) because it has the fewest transactions. East has the lowest average sale (4,790.09).
- **Sales reps:** David leads (1,141,737.36), Charlie is lowest (860,811.48). Performance depends strongly on the rep and region pairing.
- **Customers:** Returning and New customers each bring about 50% of revenue.
- **Correlations:** only `Unit_Cost` and `Unit_Price` are strongly related (r = 0.995). `Sales_Amount` has almost no correlation with quantity (-0.04), discount (0.02) or price (0.01).
- **Discounts:** average about 15% (range 0-30%) with no measurable lift in sales or quantity.
- **Seasonality:** strongest months are January, October and November 2023, weakest are September and February (about 29% peak-to-trough difference).
- **Data limitations:** no profit column, no customer ID, and `Sales_Amount` does not follow quantity x price, so it should be validated before financial use.

---

## Business Recommendations

1. **Grow Food order volume** - Food has the highest average sale but the fewest transactions.
2. **Increase sales activity in the South and basket size in the East** - South has the fewest orders, East has the lowest average sale.
3. **Test discount levels before continuing broad discounting** - discounts show no measurable effect on sales or quantity.
4. **Strengthen customer retention** - returning customers generate about half of revenue.
5. **Plan inventory and promotions around the seasonal cycle** - stock up before January and October-November, run campaigns in February and September.
6. **Rebalance sales territories and coach low-ticket reps** - results vary sharply by rep and region pairing.
7. **Validate `Sales_Amount` and capture profit and customer ID data** - needed for profit and customer concentration analysis.

---

## Repository Structure

```
├── DataScience_Task1_EDA.ipynb       # Jupyter Notebook with all code and outputs
├── sales_data.csv                    # Original dataset
├── sales_data_cleaned.csv            # Dataset after cleaning
├── numerical_feature_summary.csv     # Summary statistics of numerical features
├── Task01_EDA_Report.pdf             # Full PDF report
├── screenshots/                      # Code and output screenshots
├── graphs/                           # Saved visualization images
└── README.md
```

---

## How to Run the Notebook

### Option 1: Locally (Jupyter Notebook)

```bash
# 1. Clone the repository
git clone [your-repository-link]
cd [repository-folder]

# 2. Install the required libraries
pip install pandas numpy matplotlib seaborn jupyter

# 3. Launch Jupyter
jupyter notebook
```

Open `DataScience_Task1_EDA.ipynb` and run the cells from top to bottom. Keep `sales_data.csv` in the same folder as the notebook, because the code reads it with `pd.read_csv('sales_data.csv')`. The first cell creates `sales_data_cleaned.csv`, which the later cells depend on, so run the cells in order.

### Option 2: Google Colab

1. Upload the notebook to [Google Colab](https://colab.research.google.com/).
2. Upload `sales_data.csv` through the Files panel on the left.
3. Run all cells in order (Runtime → Run all).

---

## Author

**Ateeb Mustapha**
Data Science Intern - Devixo Solutions
GitHub: https://github.com/ate-eb
