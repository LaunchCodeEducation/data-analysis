SQL Part 1 - Introduction and Azure Data Studio
===============================================

.. admonition:: Note

   As you read through the articles in the SQL lessons, you may find that you want to try out the queries the authors describe. 
   You have access to a database called ``AdventureWorks2019`` if you would like to try out some of these queries. 
   Doing so is additional practice separate from the exercises.


Read the following articles, follow along where instructed:

Introduction to SQL
-------------------

#. `What is SQL? <https://www.youtube.com/watch?v=27axs9dO7AE>`__
#. `What Is a Database? <https://www.oracle.com/database/what-is-database/>`__
#. `Learn to write SQL queries in 5 minutes! <https://medium.com/geekculture/writing-your-first-sql-query-610da7a5afea>`__
#. `Learn to write basic SQL Queries. <https://www.sqlshack.com/learn-to-write-basic-sql-queries/>`__
#. `SQL Basics — Hands-On Beginner SQL Tutorial Analyzing Bike-Sharing <https://www.dataquest.io/blog/sql-basics/>`__
   
   a. As you read this article, skip the "Installation and Setup" section.
   #. Stop at the "Join" section.  
   #. The article uses SQLite3, while we are using T-SQL.  The biggest difference in sytax is that T-SQL uses ``TOP`` instead of ``LIMIT``.


**Additional Resources**

Optional reading:

#. `Glossary: Databases and SQL <https://swcarpentry.github.io/sql-novice-survey/reference.html>`__

#. `SQL Tutorial: Essential SQL For The Beginners <https://www.sqltutorial.org/>`__

Check Your Understanding
------------------------

.. admonition:: Question

   What does SQL stand for?

.. admonition:: Question

   Why do we use SQL?

.. admonition:: Question

   Is Microsoft Excel a database?

   a. True
   b. False


.. admonition:: Question

   How are a Relational Database's items structured?

.. admonition:: Question

   What does the ``*`` return?

   .. sourcecode:: SQL

      SELECT * 
      FROM TABLE;

.. admonition:: Question

   Match the following terms:

   .. list-table::
      :align: left
  
      * - **Table**
        - Command which is used to retrieve the desired information.
      * - **Row**
        - Collection of data.
      * - **Column**
        - Known as a tuple/record. 
      * - **Query**
        - Represents a unique field.

.. admonition:: Question

   Match the following Keyword with its definition:

   .. list-table::
      :align: left
  
      * - ``WHERE``
        - Filters the data that falls into the defined begin and end value.
      * - ``SELECT``
        - Sort the data according to the specified column.
      * - ``FROM``
        - Filter the data according to specified conditions.
      * - ``BETWEEN``
        - Used to eliminate duplicate data from the specified columns.
      * - ``ORDER BY``
        - Used to retrieve data from the data table.
      * - ``DISTINCT``
        - Specify the table name to retrieve data from.

.. admonition:: Question

   What does the Keyword ``AS`` do?

.. admonition:: Question

   In T-SQL what expression would return the first 50 rows?

