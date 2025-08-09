[⬅️ Home](README.md) | [⬅️ Previous](02-select-columns.md) | [Next ➡️](04-count.md)

# 3. ORDER BY

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
```

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

## Questions

1. Retrieve all employee names and salaries, ordered by salary in ascending order.

   * Expected Output:

     | name          | salary   |
     | ------------- | -------- |
     | Charlie Davis | 47000.00 |
     | Diana Garcia  | 51000.00 |
     | Hannah Lee    | 54000.00 |
     | Alice Johnson | 55000.00 |
     | George Clark  | 58000.00 |
     | Bob Smith     | 62000.00 |
     | Fiona White   | 68000.00 |
     | Ethan Brown   | 72000.00 |

2. Retrieve all employee names and hire dates, ordered by hire\_date in descending order.

   * Expected Output:

     | name          | hire\_date |
     | ------------- | ---------- |
     | Fiona White   | 2021-08-22 |
     | George Clark  | 2020-10-12 |
     | Charlie Davis | 2020-01-20 |
     | Bob Smith     | 2019-07-01 |
     | Hannah Lee    | 2019-02-14 |
     | Alice Johnson | 2018-03-15 |
     | Diana Garcia  | 2017-11-10 |
     | Ethan Brown   | 2016-05-30 |

3. Retrieve all columns ordered by department in ascending order.

   * Expected Output (Partial View):

     | id | name          | department | salary   | hire\_date | is\_active |
     | -- | ------------- | ---------- | -------- | ---------- | ---------- |
     | 5  | Ethan Brown   | IT         | 72000.00 | 2016-05-30 | TRUE       |
     | 6  | Fiona White   | IT         | 68000.00 | 2021-08-22 | FALSE      |
     | 4  | Diana Garcia  | HR         | 51000.00 | 2017-11-10 | TRUE       |
     | 2  | Bob Smith     | Marketing  | 62000.00 | 2019-07-01 | TRUE       |
     | 7  | George Clark  | Marketing  | 58000.00 | 2020-10-12 | TRUE       |
     | 1  | Alice Johnson | Sales      | 55000.00 | 2018-03-15 | TRUE       |
     | 3  | Charlie Davis | Sales      | 47000.00 | 2020-01-20 | FALSE      |
     | 8  | Hannah Lee    | Sales      | 54000.00 | 2019-02-14 | TRUE       |

4. Retrieve the `name` and `salary` columns for all employees, ordered by salary descending, but only show the first 5 rows. (Optional: use `LIMIT`)

5. Retrieve all columns ordered by department ascending, then by salary descending within each department.

   * Expected Output (Partial View):

     | id | name          | department | salary   | hire\_date | is\_active |
     | -- | ------------- | ---------- | -------- | ---------- | ---------- |
     | 5  | Ethan Brown   | IT         | 72000.00 | 2016-05-30 | TRUE       |
     | 6  | Fiona White   | IT         | 68000.00 | 2021-08-22 | FALSE      |
     | 4  | Diana Garcia  | HR         | 51000.00 | 2017-11-10 | TRUE       |
     | 2  | Bob Smith     | Marketing  | 62000.00 | 2019-07-01 | TRUE       |
     | 7  | George Clark  | Marketing  | 58000.00 | 2020-10-12 | TRUE       |
     | 1  | Alice Johnson | Sales      | 55000.00 | 2018-03-15 | TRUE       |
     | 8  | Hannah Lee    | Sales      | 54000.00 | 2019-02-14 | TRUE       |
     | 3  | Charlie Davis | Sales      | 47000.00 | 2020-01-20 | FALSE      |

---

## Common Mistakes & Explanations

| Mistake                                                  | Explanation                                                                    |
| -------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Forgetting ASC or DESC                                   | By default, `ORDER BY` sorts ascending; specify DESC to reverse.               |
| Trying to order by columns not in SELECT                 | Usually allowed but depends on SQL dialect; best to include columns in SELECT. |
| Using `ORDER BY` without commas between multiple columns | Separate columns with commas to order by multiple columns.                     |

---

Practice ordering results to control the presentation and insights from your queries!

---

[⬅️ Home](README.md) | [⬅️ Previous](02-select-columns.md) | [Next ➡️](04-count.md)
