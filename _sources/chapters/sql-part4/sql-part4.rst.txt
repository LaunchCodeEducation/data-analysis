SQL Part 4 - Subqueries, UNION, INTERSECT, EXCEPT
=================================================

The articles below share how to use subqueries in queries that go beyond a SELECT statement. We will go more in-depth on these other types of statements in the next lesson. For now, focus on the rules of subqueries.

Subqueries
----------

1. `Subqueries (SQL Server) <https://docs.microsoft.com/en-us/sql/relational-databases/performance/subqueries?view=sql-server-ver15>`__.

2. `SQL - Sub Queries <https://www.tutorialspoint.com/sql/sql-sub-queries.htm>`__.

UNION, INTERSECT, EXCEPT
------------------------

1. `SQL Union, Intersect, and Except – The Ultimate Guide <https://www.essentialsql.com/sql-union-intersect-except>`__.

Correlated Subqueries
---------------------

1. `SQL Correlated Subqueries <https://www.geeksforgeeks.org/sql-correlated-subqueries>`__.


Check Your Understanding
------------------------

.. admonition:: Question

   Every statement that uses a subquery can be re-written as a join. 

   a. True
   b. False

.. admonition:: Question

   A subquery cannot use **ORDER BY**, but the main query can.

   a. True
   b. False

.. admonition:: Question

   Match the operator to the result set:

   .. list-table::
      :align: left
  
      * - **INTERSECT**
        - Combined rows from both queries.
      * - **EXCEPT**
        - Only keeps rows in common with both queries.
      * - **UNION**
        - Keeps rows from left query that aren't in common with right query.

.. admonition:: Question

   **UNION** combines columns and joins combine rows.

   a. True
   b. False

.. admonition:: Question

   What is the difference between a correlated subquery and a nested subquery?
