PySpark PostgreSQL Integration
This script demonstrates an integration between PySpark and PostgreSQL for data extraction, transformation, and storage.

Overview
The code connects to a local PostgreSQL database, fetches data from multiple tables, performs transformations, and exports it into a new PostgreSQL schema. It involves the following steps:

Connection Setup:

Establishes a connection to a PostgreSQL database using psycopg2.
Initializes Spark session with findspark for PySpark integration.
Data Retrieval:

Executes SQL queries to fetch data from a specified table (orders).
Reads CSV files (orders.csv, order_items.csv, products.csv, customers.csv) using PySpark to create DataFrames.
Data Processing:

Joins the different DataFrames (orders, order_items, products, customers) into a single DataFrame (order_details) using PySpark SQL capabilities.
Converts the resulting PySpark DataFrame into a Pandas DataFrame for data analysis.
Schema Definition and Database Creation:

Determines data types and creates corresponding tables in a target PostgreSQL schema (test).
Defines schema creation queries and executes them using psycopg2.
Data Insertion:

Converts Pandas DataFrames into tuples for bulk insertion into the respective PostgreSQL tables.
Executes bulk insertion queries using executemany() for efficient data transfer.
Data Visualization:

Generates a bar chart using Matplotlib to visualize sampled data (order_status vs count_of_order_status).
Post-Processing:

Renames a table within the PostgreSQL schema using an ALTER TABLE statement.
Prerequisites
Python 3.x
PostgreSQL
PySpark
Matplotlib
Pandas
psycopg2
Usage
Install the required dependencies.
Ensure PostgreSQL is running and accessible.
Update db_credentials with appropriate PostgreSQL connection details.
Adjust file paths for CSV files if necessary.
Run the script.
Notes
Ensure proper data type mapping in map_data_type() function for PostgreSQL schema creation.
Modify queries and data processing steps to suit your specific database and requirements.
Review and customize SQL queries according to your dataset's structure and relationships.
