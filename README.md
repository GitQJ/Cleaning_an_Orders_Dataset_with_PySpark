# Cleaning_an_Orders_Dataset_with_PySpark
Stepped into a data engineer's shoes and master data cleaning with PySpark on an e-commerce orders dataset

Built a PySpark data cleaning pipeline that turns raw e-commerce order data into a model-ready Parquet file, applying business rules for time of day, discontinued products and location features.

# CONTEXT
Raw order data had to be cleaned before it could feed a sales forecasting model. The brief set out the rules: remove invalid orders, standardise text, and engineer new features.

# MY ROLE
I covered reading, cleaning, feature creation, validation and export.

# WHAT I DID
• Read orders_data.parquet into Spark and checked the schema and data types (185950 entries)
• Removed orders placed between 12am and 5am, then converted order_date from timestamp to date
• Created a time_of_day feature (morning, afternoon, evening) with conditional logic on the order hour
• Dropped rows for a discontinued product (TV) and standardised product and category to lowercase
• Extracted purchase_state from the address string with split and array operations, then counted distinct states
• Exported the result as orders_data_clean.parquet

# RESULTS
• 185950 raw rows reduced to 170921 clean rows (8.1% removed)
• 8 distinct US states identified across orders
• 2 new features (time_of_day, purchase_state) and a clean date column ready for time-series work
• Reusable, column-level transformations instead of manual edits

# TECH STACK
Python, PySpark, Spark SQL functions, Parquet
