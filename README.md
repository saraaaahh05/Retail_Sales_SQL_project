**Retail_Sales_SQL_project**
Retail Sales Analysis using SQL
Project Overview

This project analyzes retail sales data using SQL to uncover business insights such as sales trends, customer behavior, and product performance. The goal is to demonstrate how SQL can be used to transform raw transactional data into meaningful insights for business decision-making.

The analysis focuses on answering key business questions like:

Which products generate the most revenue?

What are the peak sales periods?

How do customer demographics affect purchasing patterns?

Which product categories perform best?

🎯 Objectives

Perform data cleaning and exploration using SQL

Analyze sales performance and trends

Identify top-performing products and categories

Understand customer purchasing behavior

Generate business insights for decision-making

🗂 Dataset Description

The dataset contains retail transaction records with the following columns:

Column Name	Description
transaction_id	Unique ID for each transaction
sale_date	Date of purchase
sale_time	Time of purchase
customer_id	Unique ID for each customer
gender	Customer gender
age	Customer age
category	Product category
quantity	Number of items purchased
price_per_unit	Price of each item
cogs	Cost of goods sold
total_sale	Total sale value
🛠 Tools & Technologies

SQL (PostgreSQL / MySQL)

pgAdmin / MySQL Workbench

GitHub for version control

📊 Key Analysis Performed
1️⃣ Data Cleaning

Checked for missing values

Verified data types

Removed or handled null records

Example:

'''sql
SELECT * 
FROM retail_sales
WHERE 
transaction_id IS NULL
OR sale_date IS NULL
OR total_sale IS NULL;
'''

2️⃣ Total Sales Analysis

Calculated the overall revenue generated from sales.

SELECT SUM(total_sale) AS total_revenue
FROM retail_sales;
3️⃣ Best Selling Product Categories

Identified which categories contribute the most to total sales.

SELECT category, SUM(total_sale) AS total_sales
FROM retail_sales
GROUP BY category
ORDER BY total_sales DESC;
4️⃣ Sales by Gender

Analyzed purchasing behavior based on gender.

SELECT gender, SUM(total_sale) AS total_sales
FROM retail_sales
GROUP BY gender;
5️⃣ Monthly Sales Trend

Understanding seasonal patterns in retail sales.

SELECT 
EXTRACT(MONTH FROM sale_date) AS month,
SUM(total_sale) AS monthly_sales
FROM retail_sales
GROUP BY month
ORDER BY month;
📈 Insights Generated

Some insights obtained from the analysis:

Certain product categories dominate revenue generation

Peak sales occur during specific months

Customer demographics influence purchasing patterns

High-value transactions contribute significantly to total revenue

📁 Project Structure
Retail-Sales-SQL-Project
│
├── dataset
│   └── retail_sales.csv
│
├── sql_queries
│   └── analysis_queries.sql
│
└── README.md
🚀 How to Run the Project

Download the dataset

Import the dataset into your SQL database

Create the table

Run the SQL queries from analysis_queries.sql

Analyze the results to generate insights

💡 Future Improvements

Build interactive dashboards using Power BI or Tableau

Perform advanced SQL analytics

Add customer segmentation analysis

Implement predictive sales forecasting

👩‍💻 Author

Sarah Kureshi

If you found this project helpful, feel free to ⭐ the repository.
