.. index::
   single: list; count

.. _list-count-examples:

``count`` Examples
==================

The general syntax for this method is:

.. sourcecode:: python

   list_name.count(search_value)

``count`` returns the number of times ``search_value`` occurs in ``list_name``.
``search_value`` may be of any data type.

If no element in the list matches ``search_value``, then ``count`` returns
``0``.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:
         
      numbers = [8, 1, 10, 2, 6, 4, 4, 1, 3, 1]
      words = ['apple', 'pear', 'banana']

      print(numbers.count(1))
      print(words.count('ear'))

   **Console Output**

   ::

      3
      0

Note that ``count()`` searches for the EXACT value placed in the ``()``. The
method does NOT search for substrings within any element. Even though ``pear``
contains the substring ``'ear'``, the two values are different.

Search Part of a List
---------------------

By taking a slice, ``count`` can search a smaller part of a list:

.. sourcecode:: python

   list_name[start_index : end_index].count(search_value)

Written this way, the method searches ``list_name`` from ``start_index`` up to
but NOT including ``end_index``.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      numbers = [8, 1, 10, 2, 6, 4, 4, 1, 3, 1]

      print(numbers[0:3].count(1))  # Searches the slice [8, 1, 10]

   **Console Output**

   ::

      1
