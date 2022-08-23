Data Manipulation
=================

.. _readingDataManipulation:

Readings
--------

The readings and exercises are a little different for this chapter.  Both have been combined into 2 
jupyter notebooks and the link can be found :ref:`here<dataManipulationNotebook>`. 

| Complete the notebooks in the following order using the readings to help you:

#. DataManipulationWorkbook
#. MergingTables 

| When finished follow the instructions :ref:`here<submitDataManipulation>` to submit your finished notebooks.

.. admonition:: Note

   The reading links are included within the notebooks you forked.

Check Your Understanding
------------------------

.. admonition:: Question

   What is the syntax for multiple aggregation functions across a single column, such as 'age'?

.. admonition:: Question

   What data type is the syntax using?

.. admonition:: Question

   What is this line of code doing with the data? 
   
   .. sourcecode:: py

      data_group = data.groupby("embark_town")

.. admonition:: Question

   What is this line of code doing with the data? 
   
   .. sourcecode:: py

      data_group = data.groupby("embark_town").agg("mean")

.. admonition:: Question

   According to pandas documentation, using a for loop is the only way to update values in a column.

   a. True
   b. False

.. admonition:: Question

   What is the syntax to rename a column?

.. admonition:: Question

   Converting numeric data to categorical data is an example of?

.. admonition:: Question

   The pivot() method is the only way to aggregate values in a table.

   a. True
   b. False

.. admonition:: Question

   Which method do you use to create a "Wide-to-Long" table?

.. admonition:: Question

   When creating a small table, you should store it in its own variable to keep your original table safe.

   a. True
   b. False

.. admonition:: Question

   When appending a new row, if it contains a column that doesn't previously exist in the original table then an error will be thrown.

   a. True
   b. False

.. admonition:: Question

   Concatenation can act on which axes?

   a. 1 and 0 
   b. 1, only 
   c. 0 only 
   d. for as many columns as the table contains.

.. admonition:: Question

   Using our flowers and garden_supply tables, write the syntax to merge a subset of columns, 
   where flowers is the right table, and garden_supply on the left. This subset should only look 
   at "Flower" and "Sold_As" only in the garden_supply table, and "Name" in the flowers table.

   a. 
   
   .. sourcecode:: py

      garden_supply[["Flower","Sold_As"]].merge(flowers[["Name"]],left_on="Flower", right_on="Name") 
   
   b. 
   
   .. sourcecode:: py
   
      flowers[["Flower", "Sold_As"]].merge(garden_supply[["Name"]], left_on="Flower", right_on="Name") 
   
   c. 
   
   .. sourcecode:: py
   
      garden_supply[["Flower", "Sold_As"]].merge(flowers[["Name"]], left_on="Name", right_on="Flowers") 
   
   
   d. 
   
   .. sourcecode:: py
   
         garden_supply[["Name"]].merge(flowers[["Flower", "Sold_As"]], left_on="Flower", right_on="Name") 

.. admonition:: Question

   The default merge in the pandas merge() function is a left merge.

   a. True
   b. False

.. admonition:: Question

   Which merge combines ALL of the rows of the merged dataframes, filling in NaN if values are missing?

.. admonition:: Question

   (1 of 2) In the merge() function, there are the following parameters: on, left_on, and right_on. 
   When would you use them?

.. admonition:: Question

   (2 of 2) What is the difference between on and left_on in the merge() function?

.. admonition:: Question

   When working with join, the right table will always be joined based on its index and not a designated column.

   a. True
   b. False

.. admonition:: Question

   The default join() type is:
   


