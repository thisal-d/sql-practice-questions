[⬅️ Home](README.md) | [⬅️ Previous](05-sum.md) | [Next ➡️](07-aliases.md)

# 6. AVG()

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

1. Calculate the average salary of all employees.

   * Expected Output:

     | avg\_salary |
     | ----------- |
     | 64500.00    |

2. Calculate the average salary of employees in the Marketing department.

   * Expected Output:

     | avg\_salary |
     | ----------- |
     | 60000.00    |

3. Calculate the average salary of active employees (`is_active = TRUE`).

   * Expected Output:

     | avg\_salary |
     | ----------- |
     | 58333.33    |

4. Retrieve the department and average salary for each department (combine with `GROUP BY`).

   * Expected Output:

     | department | avg\_salary |
     | ---------- | ----------- |
     | Sales      | 52000.00    |
     | Marketing  | 60000.00    |
     | HR         | 51000.00    |
     | IT         | 70000.00    |

5. Calculate the average salary of employees hired after 2018-01-01 (combine with `WHERE`).

   * Expected Output:

     | avg\_salary |
     | ----------- |
     | 54750.00    |

---

## Common Mistakes & Explanations

| Mistake                                                     | Explanation                                                     |
| ----------------------------------------------------------- | --------------------------------------------------------------- |
| Using `AVG()` on non-numeric columns                        | `AVG()` only works with numeric columns like `salary`.          |
| Forgetting to use `GROUP BY` when aggregating by department | `GROUP BY` groups the rows for aggregate calculations.          |
| Mixing `WHERE` and `HAVING` incorrectly                     | `WHERE` filters before aggregation, `HAVING` after aggregation. |

---

Practice calculating averages to gain insight into numeric data distributions!

---

[⬅️ Home](README.md) | [⬅️ Previous](05-sum.md) | [Next ➡️](07-aliases.md)
