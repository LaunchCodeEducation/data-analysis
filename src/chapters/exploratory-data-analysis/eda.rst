Exploratory Data Analysis
=========================

Read the following articles, follow along where instructed:

.. admonition:: tip
  
  For Medium articles: if you run out of free articles, open the page in an incognito window

Exploring Data with Python
--------------------------

1. `Exploratory data analysis in Python <https://towardsdatascience.com/exploratory-data-analysis-in-python-c9a77dfa39ce>`__.

* Key Takeaways: Outline of common steps used in EDA, note that there is no one process for performing EDA, 
  it all depends on the dataset and your questions.
* Just read and follow the steps for comprehension, don't need to do the tutorial.
* Stop at #8: “Detecting Outliers”

Get to Know Your Data
---------------------

2. `Getting to know your data <https://medium.com/@shanegary/getting-to-know-your-data-9e42935e7f60>`__.

* Key Takeaways: Questions to better understand why the data was collected.
* *Suggested Reading:* `Data Types in Statistics <https://towardsdatascience.com/data-types-in-statistics-347e152e8bee>`__.

  * Key Takeaways: Definitions for discrete, continuous and categorical data.

Python Pandas
-------------

3. `Python Pandas Tutorial: A Complete Introduction for Beginners <https://www.learndatasci.com/tutorials/python-pandas-tutorial-complete-introduction-for-beginners/>`__.

* You do not need to install pandas, it comes with the Anaconda package.
* Try coding along with the article 
* Stop at “Handling Duplicates” header

Statistics in Pandas
--------------------

4. `Basic statistics in pandas DataFrame <https://medium.com/@kasiarachuta/basic-statistics-in-pandas-dataframe-594208074f85>`__.

* Key takeaway: Using pandas DataFrame; with examples
  
What is a Dataframe?
--------------------

A Pandas dataframe is similar to a Python dictionary. The column names are like keys and the values are the data for that column.  This diagram illustrates the different components of a dataframe.

.. figure:: figures/diagramPandasDataframe.png
   :alt: Diagram of a Pandas Dataframe.

Credit for the above diagram and for more information about Pandas Dataframes `visit here <https://www.w3resource.com/python-exercises/pandas/index-dataframe.php>`__.

| The column values are called a Pandas series. Here is how Pandas series are used to build a dataframe.

.. figure:: figures/diagramPandasSeries.png
   :alt: Diagram of how Pandas series build a dataframe.  

Credit for the above diagram and for more information about Pandas Series `visit here <https://www.datasciencemadesimple.com/create-series-in-python-pandas/>`__.

Check Your Understanding
------------------------

.. admonition:: Question

  What is the pandas function used to return the number of rows and columns in a dataframe?

.. admonition:: Question
  
  Column names cannot be changed in dataframes?

  a. True
  b. False

.. admonition:: Question

  What can knowing the data types present in a data set tell us about the data being presented?

.. admonition:: Question

  What is the Pandas method for reading a csv?

.. admonition:: Question

  Visualized below is the “purchases” dataframe . What is the pandas syntax to select for Robert's data?

  .. figure:: figures/purchaseDataframe.png
   :alt: Dataframe showing name of person and if they purchased apples and/or oranges.

.. admonition:: Question

  How do we view only the first 13 rows of a dataframe?

.. admonition:: Question

  A dataframe column is a series?

  a. True
  b. False

.. admonition:: Question  

  Which pandas function will print the number of records, three quartiles, mean, standard deviation, minimum and maximum values of  a dataframe?

  a. .describe() 
  b. .index() 
  c. .statistics() 
  d. .head() 
