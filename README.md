# Filtering

Exploratory data analysis of a global e-commerce sales dataset, focused on data selection, filtering, and feature engineering with `pandas` culminating in a set of business insights on top-performing categories, regions, and products.

## 📁 Dataset

The notebook works with `global_ecommerce_sales.csv`, containing order-level e-commerce data with fields such as:

- `Order_ID`, `Order_Date`, `Customer_Name`, `Customer_Segment`
- `Country`, `Region`
- `Product_Category`, `Product_Name`, `Quantity`, `Unit_Price`
- `Discount_Percent`, `Total_Sales`, `Shipping_Cost`, `Profit`
- `Payment_Method`

> Note: the CSV file is included in this repo ( download it and update the file path in the notebook) before running.

## 🔍 What the notebook does

**1. Data Understanding**
- Loads the dataset and inspects its shape, columns, data types, missing values, and duplicates
- Generates summary statistics with `df.describe()`

**2. Selection & Filtering**
- Selects specific columns of interest
- Filters rows using conditions (e.g. orders with `Quantity > 2`, high-profit `Technology` orders)
- Explores value counts for categorical fields like `Product_Category` and `Region`
- Uses `.loc` for conditional column-value lookups and multi-condition filtering
- Sorts orders by `Profit` to surface top performers

**3. Feature Engineering**
- `Gross_Sales` = `Unit_Price × Quantity`
- `Net_Sales` = `Gross_Sales` adjusted for `Discount_Percent`
- `Profit_Margin` = `Profit / Net_Sales × 100`
- Confirms that `Net_Sales` and the existing `Total_Sales` column are equivalent

**4. Grouping & Aggregation**
- Aggregates `Total_Sales` and `Profit` by `Product_Category`, `Region`, and `Product_Name`
- Identifies the best-performing category, region, and product by total profit

## 📊 Final Business Insights

- **Best Category:** Furniture has highest total profit and sales
- **Strongest Region:** Europe has highest overall profit
- **Product to Promote:** Ergonomic Office Chair has highest total profit among all products
- Office furniture products consistently rank among top performers in both sales and profit
- Some low-priced office supplies show very low or negative profit, suggesting pricing/cost review is needed
- Recommendation: focus marketing on high-profit products while optimizing underperforming ones

## 🛠️ Tech Stack

- Python 3
- pandas
- Google Colab

## 🚀 Running the Notebook

You can open the notebook directly in Google Colab or run it locally:

```bash
pip install pandas
jupyter notebook Filtering.ipynb
```

Make sure `global_ecommerce_sales.csv` is available at the path referenced in the first cells.
