#  SQL Project: Data Analysis on Maven Movies Database

##  Overview

This project is a comprehensive SQL-based analysis using the **Maven Movies** dataset (a variation of the Sakila database). It includes DDL, DML, joins, normalization, functions, and stored procedures to extract meaningful business insights for a fictional DVD rental company.


##  Dataset

- **Database**: Maven Movies (MySQL)
- **Tables**:
  - `film`, `actor`, `customer`, `rental`, `payment`, `store`, `inventory`, `category`, `staff`, etc.
- **Use Case**: Simulates the operations of a DVD rental store.

##  Objectives

- Design and create tables with constraints
- Perform relational queries using joins
- Normalize database tables to 1NF and 2NF
- Build stored procedures, views, and functions
- Analyze business metrics such as sales, rentals, and customer behavior


##  Technologies

- MySQL (Workbench / CLI)
- SQL (DDL, DML, Views, CTEs, Procedures)
- ER Diagram Tools (e.g., dbdiagram.io)
- Git + GitHub for version control


##  SQL Concepts Implemented

- Table creation with constraints
-  Joins (`INNER`, `LEFT`, `SELF`)
-  Aggregate functions: `SUM`, `AVG`, `COUNT`, `GROUP BY`
-  Subqueries & nested queries
-  Views & Common Table Expressions (CTEs)
-  Stored Procedures & Functions
-  Data Normalization (1NF, 2NF)


##  Sample Queries

###  Total Revenue by Category
```sql
SELECT c.name AS category, SUM(p.amount) AS total_sales
FROM payment p
JOIN rental r ON p.rental_id = r.rental_id
JOIN inventory i ON r.inventory_id = i.inventory_id
JOIN film f ON i.film_id = f.film_id
JOIN film_category fc ON f.film_id = fc.film_id
JOIN category c ON fc.category_id = c.category_id
GROUP BY c.name
ORDER BY total_sales DESC;




Author
Name: jagrati sen
Email: jagratisen.2116@gmail.com
