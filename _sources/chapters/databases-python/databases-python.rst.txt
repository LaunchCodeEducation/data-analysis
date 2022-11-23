Working with Databases in Python
================================

Reading
-------

Read the following articles:

`Working with database using Pandas <https://www.geeksforgeeks.org/working-with-database-using-pandas/>`__.

`How to Use Pandas to Access Databases <https://medium.com/jbennetcodes/how-to-use-pandas-to-access-databases-e4e74e6a329e>`__.

`Python - Databases and SQL <https://www.tutorialspoint.com/python_network_programming/python_databases_and_sql.htm>`__.

Check Your Understanding
------------------------

.. admonition:: Question

   What is the correct code for establishing the connection to a database?

   a.
   
   .. code-block:: python3
      
      con = sl.connect('database.db')

   b.
   
   .. code-block:: python3
      
      con = sl.connection('database.db')
  
   c.
   
   .. code-block:: python3
    
      con = sl.connect(database.db)

   d.
   
   .. code-block:: python3
      
      con = pd.connect('database.db')

.. admonition:: Question

   **read_sql_query()** has 2 arguments. What are they?

.. admonition:: Question

   Is it a good practice to attempt to first explore a database with a database client or Pandas? Why?

.. admonition:: Question

   Is it good practice to limit the fields and/or records to retrieve when setting up a dataframe from a database table?

.. admonition:: Question

   Should the database server handle joins or Pandas? Why?

.. admonition:: Queston

   If your connection is named **con**, and you want to add a new record to the table, **costco_finds**, what would your code look like?

.. admonition:: Question

   If you wanted to print the records in the **costco_finds** table, what would your code look like?

.. admonition:: Question

   If you wanted to change the name of one of your **costco finds**, what would your code look like?

.. admonition:: Question

   If you wanted to remove a record from **costco_finds**, what would your code look like?