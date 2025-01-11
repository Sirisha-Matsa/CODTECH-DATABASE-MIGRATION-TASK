# CODTECH-DATABASE MIGRATION-TASK

Name: Sirisha Matsa

Company: CODTECH IT SOLUTIONS

ID: CT08DQC

Domain: SQL

Duration: DEC-2024 TO JAN-2025

Mantor: NEELA SANTOSH KUMAR

# OVERVIEW OF THE PROJECT:

***PROJECT:DATABASE MIGRATION***

**OBECTIVE:**

To seamlessly migrate data between MySQL and PostgreSQL databases, ensuring data integrity, consistency, and relational integrity. The objective includes exporting data from MySQL, importing it into PostgreSQL, validating row counts and relationships, and automating the process using Python for efficiency and accuracy in database transition.

# KEY COMPONENTS:

***1. Export Data from MySQL***

**SQL Code:**

  * The SELECT ... INTO OUTFILE statements export data from the MySQL customers and orders tables into CSV files.

**Key Points:**

  * CSV fields are delimited by , and enclosed in ".
  * Lines are terminated by \n.

**Example Output:**

  /path/to/customers.csv and /path/to/orders.csv will contain table data in CSV format.

***2. Import Data into PostgreSQL***

**SQL Code:**

  * The COPY command imports the CSV files into PostgreSQL tables (customers and orders).

**Key Points:**

  * Uses the DELIMITER ',' for CSV parsing.
  * The CSV HEADER option assumes the CSV contains column headers.
    
**Expected Result:**

  *The data is loaded into PostgreSQL, maintaining the schema structure.

***3. Validate Data Integrity***

**Row Count Validation:**

  * The COUNT(*) queries ensure that the total number of rows in each table matches between MySQL and PostgreSQL.
    
**Foreign Key Relationship Validation:**

  * The LEFT JOIN query identifies any customer_id values in the orders table that do not exist in the customers table.
    
**Expected Result:**

  * No missing or invalid foreign key relationships.

***4. Python Script for Automation***

**Code Overview:**

  * MySQL Connection: Uses sqlalchemy to connect to the MySQL database.
  * PostgreSQL Connection: Uses sqlalchemy to connect to the PostgreSQL database.
    
**Data Migration:**

  * Reads data from the MySQL tables (customers and orders) into pandas DataFrames.
  * Writes the DataFrames to PostgreSQL tables using to_sql.
    
**Key Points:**

  * Libraries: Requires pandas and sqlalchemy.
  * Automation: Simplifies the migration process by avoiding manual exports/imports.
