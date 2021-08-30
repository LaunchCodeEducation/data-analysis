
The ``statistics`` Module
=========================

The ``statistics`` module contains the kinds of functions you would find in any
statistics textbook---like finding the **mean** or the **standard deviation** of
a data sample.

Here are two items from the statistics module in action:

.. replit:: python
   :slug: Stats-Mod

   import statistics as stats
   
   dog_ages = [ 6, 2, 1, 4, 6, 12, 11, 9, 2, 3, 7]

   print(stats.mean(dog_ages))
   print(stats.stdev(dog_ages))
   print(stats.variance(dog_ages))

**Console Output**

::

   5.7272727272727275
   3.7440862460928725
   14.01818181818182

``stats.mean()`` calculates the mean, or average, of a given data set.  
``stats.stdev()`` calculates the `standard deviation <https://www.khanacademy.org/math/statistics-probability/summarizing-quantitative-data/variance-standard-deviation-population/a/calculating-standard-deviation-step-by-step>`_ of a data set.
``stats.variance()`` calculates the `variance <https://www.investopedia.com/terms/v/variance.asp>`_ of a data set.  
Using a module, the formulas are already available, along with code to iterate through your data sets.  
This saves you a lot of time and allows to you work on other areas of your program where you want to use the 
output of the module methods.

`W3 schools <https://www.w3schools.com/python/module_statistics.asp>`_ has a complete list of all the items in the ``statistics`` module.

