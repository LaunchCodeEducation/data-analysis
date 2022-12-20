Exploratory Data Analysis
=========================

Read the following articles, follow along where instructed.  

.. admonition:: Note
    
  You do not need to install ``pandas``, it comes with ``Anaconda``.  

.. admonition:: Tip
  
  For Medium articles: if you run out of free articles, open the page in an incognito window.

Exploring Data with Python
--------------------------

Code along with this article.  

#. `Exploratory data analysis in Python <https://towardsdatascience.com/exploratory-data-analysis-in-python-c9a77dfa39ce>`_.
#. Stop at Step #8 "Detecting Outliers".

Get to Know Your Data
---------------------

#. `Getting to know your data <https://medium.com/@shanegary/getting-to-know-your-data-9e42935e7f60>`_.
#. `Data Types in Statistics <https://towardsdatascience.com/data-types-in-statistics-347e152e8bee>`_.


Python ``pandas``
-----------------

Code along with this article.  

#. `Python Pandas Tutorial: A Complete Introduction for Beginners <https://www.learndatasci.com/tutorials/python-pandas-tutorial-complete-introduction-for-beginners/>`_
#. Stop at "Handling Duplicates".

Statistics in ``pandas``
------------------------

#. `Basic statistics in pandas DataFrame <https://medium.com/@kasiarachuta/basic-statistics-in-pandas-dataframe-594208074f85>`__.
  
What is a ``DataFrame``?
------------------------

A ``pandas DataFrame`` is similar to a Python dictionary. The column names are like keys and the values are the data for that column. 

.. figure:: figures/diagramPandasDataframe.png
  :alt: Diagram of a Pandas Dataframe.
  
  
  For more information about ``pandas DataFrames`` and the diagram above, `visit w3resource <https://www.w3resource.com/python-exercises/pandas/index-dataframe.php>`__.

| The column values are called a ``pandas Series``. Here is how ``pandas Series`` are used to build a dataframe.

.. figure:: figures/diagramPandasSeries.png
  :alt: Diagram of how ``pandas Series``  a dataframe.  

  For more information about ``pandas Series`` and diagram above, `visit w3resource <https://www.datasciencemadesimple.com/create-series-in-python-pandas/>`__.

Check Your Understanding
------------------------

.. admonition:: Question

  What is the ``pandas`` function used to return the number of rows and columns in a ``DataFrame``?

.. admonition:: Question
  
  Column names cannot be changed in a ``DataFrame``?

  a. True
  b. False

.. admonition:: Question

  What can knowing the data types present in a data set tell us about the data being presented?

.. admonition:: Question

  What is the ``pandas`` method for reading a CSV file type?

.. admonition:: Question

  Visualized below is the “purchases” ``DataFrame`` . What is the ``pandas`` syntax to select for Robert's data?

  .. figure:: figures/purchaseDataframe.png
   :alt: DataFrame showing name of person and if they purchased apples and/or oranges.

.. admonition:: Question

  How do we view only the first 13 rows of a ``DataFrame``?

.. admonition:: Question

  A ``DataFrame`` column is a ``Series``?

  a. True
  b. False

.. admonition:: Question  

  Which ``pandas`` function will print the number of records, three quartiles, mean, standard deviation, minimum and maximum values of a ``DataFrame``?

  a. ``.describe()`` 
  b. ``.index()`` 
  c. ``.statistics()`` 
  d. ``.head()`` 
