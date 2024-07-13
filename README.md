# Iris Dataset SQL Queries

This repository contains SQL queries for analyzing the famous Iris dataset. The Iris dataset consists of 150 samples of iris flowers, where each sample includes measurements of sepal length, sepal width, petal length, petal width, and the corresponding iris species.

The purpose of this repository is to demonstrate SQL queries for typical data analysis tasks using the Iris dataset. These queries cover basic SQL operations, filtering, aggregation, and advanced querying techniques such as subqueries and ordering.

## Dataset Description

- **Table Name:** iris
- **Columns:**
  - `sepal_l` (Sepal Length)
  - `sepal_w` (Sepal Width)
  - `petal_l` (Petal Length)
  - `petal_w` (Petal Width)
  - `class` (Species of iris)

## Queries

### Basic Operations

1. **Creating Table:**
   ```sql
   CREATE TABLE iris (
       sepal_l FLOAT,
       sepal_w FLOAT,
       petal_l FLOAT,
       petal_w FLOAT,
       class VARCHAR(20)
   );
   ```

2. **Selecting All Data**
    ```sql
    SELECT * FROM iris;
    ```

3. **Filtering Data by Sepal Width greater than 3.5**
    ```sql
    SELECT * FROM iris WHERE sepal_w > 3.5;
    ```

### Aggregation Queries

4. **Average Petal Length by Class**
 
     ```sql
      SELECT class, AVG(petal_l) AS average_petal_length FROM iris GROUP BY class;
     ```
6. **Top 3 Highest Average Petal Lengths**
     ```sql
       SELECT class, AVG(petal_l) AS average_petal_length
       FROM iris GROUP BY class ORDER BY average_petal_length DESC LIMIT 3;
     ```
7. **Top 3 Lowest Average Petal Lengths**
     ```sql
       SELECT class, AVG(petal_l) AS average_petal_length
       FROM iris GROUP BY class ORDER BY average_petal_length LIMIT 3;
     ```
8. **Top 2 Lowest Average Sepal Widths**
    ```sql
      SELECT class, AVG(sepal_w) AS average_sepal_width
      FROM iris GROUP BY class ORDER BY average_sepal_width LIMIT 2;
    ```
9. **Maximum Petal Length of Each Class**
     ```sql
       SELECT class, MAX(petal_l) AS max_petal_length FROM iris GROUP BY class;
     ```
10. **Minimum Sepal Length of Each Class**
      ```sql
        SELECT class, MIN(sepal_l) AS min_sepal_length FROM iris GROUP BY class;
      ```
11. **Sepal Width greater than Average Sepal Width**
      ```sql
        SELECT class, sepal_w FROM iris WHERE sepal_w > (SELECT AVG(sepal_w) FROM iris);
      ```
