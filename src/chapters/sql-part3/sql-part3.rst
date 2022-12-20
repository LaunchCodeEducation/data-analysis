SQL Part 3 - Joins
==================

Read the following articles, and watch the videos:

SQL ``JOINS``
-------------
#. `SQL join types <https://www.metabase.com/learn/sql-questions/sql-join-types>`__.
#. `SQL | Join (Inner, Left, Right and Full Joins) <https://www.geeksforgeeks.org/sql-join-set-1-inner-left-right-and-full-joins/>`__.
#. `SQL Joins Explained |¦| Joins in SQL |¦| SQL Tutorial Part 1 <https://www.youtube.com/watch?v=9yeOJ0ZMUYw>`__.
#. `SQL Joins Examples |¦| Joins in SQL |¦| SQL Tutorial Part 2 <https://www.youtube.com/watch?v=Jh_pvk48jHA>`__.

``HAVING`` clause
-----------------

The ``HAVING`` clause is very similar to a ``WHERE`` clause in that it is used to filter result sets. However, we cannot use the ``WHERE`` clause with aggregate functions. Instead, we have to use the ``HAVING`` clause. If you want to use an aggregate function with a ``join``, then you need to make use of this new clause. The ``HAVING`` clause is often used with ``GROUP BY``.

#. `SQL HAVING <https://www.sqltutorial.org/sql-having/>`__.
#. `Intermediate SQL Tutorial | Having Clause <https://www.youtube.com/watch?v=tYBOMw7Ob8E>`__.

Check Your Understanding
------------------------

.. admonition:: Question

   What does an ``INNER JOIN`` do?

   a. Returns results with matching rows in both tables 
   b. Returns results with all the rows from the left table with null values for unmatched rows from the right table 
   c. Returns results with all the rows from the right table with null values for unmatched rows from the left table 
   d. Returns results from all the rows from both tables with null values filled in for all unmatched rows. 

.. admonition:: Question

   What does a ``FULL JOIN`` or ``OUTER JOIN``  do?

   a. Returns results with matching rows in both tables 
   b. Returns results with all the rows from the left table with null values for unmatched rows from the right table 
   c. Returns results with all the rows from the right table with null values for unmatched rows from the left table 
   d. Returns results from all the rows from both tables with null values filled in for all unmatched rows 

.. admonition:: Question
   
   In your own words what is the difference between a ``RIGHT JOIN`` and a ``LEFT JOIN``?

.. admonition:: Question

   In what order do the following clauses go when writing a query?

   a. ``SELECT, WHERE, HAVING, GROUP BY``
   b. ``SELECT, HAVING, WHERE, GROUP BY`` 
   c. ``SELECT, WHERE, GROUP BY, HAVING``
   d. ``SELECT, HAVING, GROUP BY, WHERE``

.. admonition:: Question

   Can you use aggregates with the ``HAVING`` Clause?

   a. True 
   b. False

.. admonition:: Question

   Can you use aggregates with the ``WHERE`` clause?

   a. True 
   b. False

.. admonition:: Question

   In your own words, what is the difference between the ``WHERE`` clause and the ``HAVING`` clause?