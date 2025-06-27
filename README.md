# etl_angela-289
# ETL Midsemester Project – Angela (ID: 289)

## Project Overview
This project demonstrates an ETL (Extract, Transform, Load) process applied to sales data. It focuses on cleaning and enriching both a full dataset and an incremental update, followed by loading the final output into a structured format for analysis.

## ETL Phases

### 1. Extract – `etl_extract.ipynb`
- Loaded `raw_data.csv` and `incremental_data.csv`.
- Used `.head()` and `.info()` to inspect data structure.
- Observed issues such as missing values and duplicate rows.

### 2. Transform – `etl_transform.ipynb`
Performed six key transformations:
1. Removed duplicate rows
2. Filled missing `customer_name` values with "Unknown"
3. Filled missing numeric values (quantity and unit_price) with their median
4. Created a new column `total_price = quantity * unit_price`
5. Converted `order_date` to datetime format
6. Filled missing `region` values with "Unspecified"

Final transformed datasets were saved as:
- `transformed/transformed_full.csv`
- `transformed/transformed_incremental.csv`

### 3. Load – `etl_load.ipynb`
- Loaded the transformed files into SQLite databases:
  - `loaded/full_data.db`
  - `loaded/incremental_data.db`
- Verified data using SQL queries (e.g., `SELECT * FROM orders LIMIT 5`)

## Tools Used
- Python
- Pandas
- SQLite (sqlite3)
- Jupyter Notebooks
