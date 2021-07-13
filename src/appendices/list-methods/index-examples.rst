.. _list-index-examples:

.. index::
   single: list; index

``index`` Examples
==================

The general syntax for this methods is:

.. sourcecode:: python

   list_name.index(value)

``index`` returns the index of the FIRST occurrence of ``value`` in the list.
If the value is not in the list, Python throws an error.

.. admonition:: Examples
   
   .. sourcecode:: python
      :linenos:

      letters = ['o', 'y', 'j', 'j', 'g', 'f', 'h', 'y', 'j', 'x']

      print(letters.index('j'))
      print(letters.index('nope!'))

   **Console Output**

   ::

      2
      ValueError: 'nope!' is not in list

Finding All Index Values
------------------------

Often, we want to return all of the index values for a given search. One way to
accomplish this is by using a loop:

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      letters = ['o', 'y', 'j', 'j', 'g', 'f', 'h', 'y', 'j', 'x']
      index_values = []
      search_value = 'j'

      for index in range(len(letters)):
         if letters[index] == search_value:
            index_values.append(index)
      
      print("{0} has indexes of {1} in the list.".format(search_value, index_values))

   **Console Output**

   ::

      j has indexes of [2, 3, 8] in the list.

.. admonition:: Note

   Returning all index values for a given search is such a common task that
   Python coders have found a short, elegant way to do it:

   .. sourcecode:: python

      index_values = [index for index in range(len(list_name)) if list_name[index] == search_value]

   This does the same thing as the ``for`` loop shown in the example above.
   (Take a close look at the code to find the ``for`` and ``if`` statements).

   We will not analyze the syntax here, but if you are curious, you can find
   an explanation `here <https://www.geeksforgeeks.org/python-ways-to-find-indices-of-value-in-list/>`__.
