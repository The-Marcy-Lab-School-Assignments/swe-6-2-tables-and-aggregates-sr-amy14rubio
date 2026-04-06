# Short Response: Creating Tables and Aggregates

Answer each question below. Write in complete sentences (3–5 per answer).

---

## Question 1

What is a data type? Why does it matter what type you assign to a column? Give an example of what could go wrong if you used the wrong type.

**Your answer:**
A **data type** is the constraint that will ensure that **all data entries** for a column will **follow a specific format**. Data types matter as they set up a **structure** for accepted data values for future developers. If data needs to be **manipulated**, then the developer would rely on the **initial data type** that was assigned to the column. For example, if a developer wanted to find the average price of all products, they wouldn't be able to do so if the prices were entered as **`TEXT` instead of a `NUMERIC` data type**.

---

## Question 2

What is a constraint? Name two constraints and explain what each one enforces.

**Your answer:**
A **constraint** is a **rule** placed on a database that **rejects** any data inputs that don't follow that rule. One constraint is `NOT NULL` which enforces that the data isn't left **blank or empty**. It ensures that the column has a **value for each row**. Another constraint is `UNIQUE` which ensures that **no two rows have the same data in the same column**.

---

## Question 3

What is the difference between `WHERE` and `HAVING`? Can you use both in the same query? If so, what does each one do?

**Your answer:**
The difference between `WHERE` and `HAVING` is that while they **both filter** through data, they are used at **different stages** in the query. Both `WHERE` and `HAVING` can be used in the same query as they filter rows at separate stages. `WHERE` filters results **before grouping**, while `HAVING` filters results **after aggregation**.

---

## Question 4

What is a seed file? Why is seeding important when working on a team?

**Your answer:**
A **seed file** populates a database from scratch, in other words it is a sort of **template** with data ready for other developers to use and manipulate. A seed file usually includes steps such as dropping and recreating databases, dropping and recreating tables, and inserting seed data. Seeding is important so that team members can **recreate the same database**, **reset the database** to its original seeded state, and allow for a \*\*streamlined system to reproduce data\*\* without having to manually input it.

---

## Question 5

You have a table called `orders` with a `customer_name` column and a `total` column. Write a SQL query that shows each customer's total spending, but only includes customers who have spent more than $100 in total.

```sql
SELECT customer_name,
SUM(total) AS total_spending
FROM orders
GROUP BY customer_name
HAVING SUM(total) > 100
```
