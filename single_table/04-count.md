
# 4. COUNT()

---

## Navigation

[Previous: ORDER BY](03-order-by.md) | [Main README](README.md) | [Next: SUM()](05-sum.md)

---

## Introduction

This section introduces the aggregate function `COUNT()`, used to count rows or non-null values in a column. You will learn how to count total rows, count distinct values, and combine counts with conditions.

---

## Table Schema & Sample Data

```sql
CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(50),
    salary DECIMAL(10,2),
    hire_date DATE,
    is_active BOOLEAN
);
````

| id | name          | department | salary   | hire\_date | is\_active |
| -- | ------------- | ---------- | -------- | ---------- | ---------- |
| 1  | Alice Johnson | Sales      | 55000.00 | 2018-03-15 | TRUE       |
| 2  | Bob Smith     | Marketing  | 62000.00 | 2019-07-01 | TRUE       |
| 3  | Charlie Davis | Sales      | 47000.00 | 2020-01-20 | FALSE      |
| 4  | Diana Garcia  | HR         | 51000.00 | 2017-11-10 | TRUE       |
| 5  | Ethan Brown   | IT         | 72000.00 | 2016-05-30 | TRUE       |
| 6  | Fiona White   | IT         | 68000.00 | 2021-08-22 | FALSE      |
| 7  | George Clark  | Marketing  | 58000.00 | 2020-10-12 | TRUE       |
| 8  | Hannah Lee    | Sales      | 54000.00 | 2019-02-14 | TRUE       |

---

## Practice Questions

### Simple Questions (Isolated Concept)

1. Count the total number of employees.

2. Count how many employees are currently active (`is_active = TRUE`).

3. Count the number of distinct departments.

### Complex Questions (Combining with Earlier Concepts)

4. Retrieve the department and count of employees in each department (combine with `GROUP BY`).

5. Count the number of employees hired after 2018-01-01 (combine with `WHERE`).

---

## Expected Outputs

### Question 1

| count |
| ----- |
| 8     |

### Question 2

| count |
| ----- |
| 6     |

### Question 3

| count |
| ----- |
| 4     |

### Question 4

| department | count |
| ---------- | ----- |
| Sales      | 3     |
| Marketing  | 2     |
| HR         | 1     |
| IT         | 2     |

### Question 5

| count |
| ----- |
| 4     |

---

## Common Mistakes & Explanations

| Mistake                                                 | Explanation                                                                                     |
| ------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Using `COUNT(column_name)` and expecting to count NULLs | `COUNT(column_name)` counts only non-null values. Use `COUNT(*)` to count all rows.             |
| Forgetting to use `GROUP BY` when aggregating by column | When counting per group, `GROUP BY` is required to avoid errors.                                |
| Using `WHERE` after aggregation functions               | Filtering with `WHERE` applies before aggregation; use `HAVING` for post-aggregation filtering. |

---

Try counting different subsets of data to better understand aggregate functions!

---

[Previous: ORDER BY](03-order-by.md) | [Main README](README.md) | [Next: SUM()](05-sum.md)
