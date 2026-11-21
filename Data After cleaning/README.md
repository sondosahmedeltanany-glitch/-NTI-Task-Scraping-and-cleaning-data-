# Data Cleaning Task

## Overview
I cleaned 5 files: `customers_master`, `products_master`, `orders`, `new_daily_batch`, `previous_days_summary`.
The code is in `cleaning.ipynb`, and every cleaned file has the name `<file>_cleaned.csv`.

After cleaning:
- `orders`: 1010 rows
- `new_daily_batch`: 316 rows

## Problems and how I solved them
| Problem | Solution |
|---|---|
| Duplicate rows | `drop_duplicates()` |
| Region, Category, Order_Status and Payment_Method written in different ways (small/capital letters, extra spaces) | `strip()` and `title()` |
| Quantity written like `3 pcs` | removed `pcs` and converted to a number |
| Discount written like `5%` | converted to `0.05` |
| Quantity zero or negative | removed these rows |
| Discount bigger than 1 or negative | removed these rows |
| Invalid order date (`not-a-date`) | removed the row |
| Ship date before order date | removed the row |
| Product_ID not found in the products file | removed these rows |
| Missing Customer_ID | filled with `Unknown` |
| Missing Ship_Date | kept empty, because these orders are Pending or Cancelled |
| Missing Unit_Price or Shipping_Cost | kept empty, because the real value is not known |
