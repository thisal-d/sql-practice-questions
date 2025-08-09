Here’s the **10. HAVING** README in the updated style:

---

[⬅️ Home](README.md) | [⬅️ Previous](09-group-by.md)

# 10. HAVING

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

1. Retrieve departments having more than 2 employees.

   * Expected Output:

     | department | count |
     | ---------- | ----- |
     | Sales      | 3     |

2. Retrieve departments having total salary greater than 120000.

   * Expected Output:

     | department | total\_salary |
     | ---------- | ------------- |
     | Sales      | 156000.00     |
     | Marketing  | 120000.00     |

3. Retrieve departments having average salary less than 60000.

   * Expected Output:

     | department | avg\_salary |
     | ---------- | ----------- |
     | Sales      | 52000.00    |
     | HR         | 51000.00    |

4. Retrieve departments having more than 1 active employee (`is_active = TRUE`).

   * Expected Output:

     | department | active\_count |
     | ---------- | ------------- |
     | Sales      | 2             |
     | Marketing  | 2             |

5. Retrieve departments having average salary greater than 60000 and count of employees greater than 1.

   * Expected Output:

     | department | avg\_salary | count |
     | ---------- | ----------- | ----- |
     | Marketing  | 60000.00    | 2     |

---

## Common Mistakes & Explanations

| Mistake                                                      | Explanation                                                 |
| ------------------------------------------------------------ | ----------------------------------------------------------- |
| Using `WHERE` to filter on aggregate conditions              | Use `HAVING` to filter grouped data, not `WHERE`.           |
| Forgetting to include aggregate functions in `HAVING` clause | Conditions in `HAVING` must involve aggregate functions.    |
| Combining multiple conditions incorrectly                    | Use `AND`/`OR` properly to combine multiple HAVING filters. |

---

Filtering groups with `HAVING` helps refine aggregated data results!

---

[⬅️ Home](README.md) | [⬅️ Previous](09-group-by.md)
