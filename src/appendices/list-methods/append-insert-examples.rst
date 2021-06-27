Adding Elements To a List
=========================

The ``append`` and ``insert`` list methods *mutate* (change) the original list.

.. index::
   single: list; append

.. _list-append-examples:

``append`` Examples
-------------------

The general syntax for this method is:

.. sourcecode:: python

   list_name.append(new_value)

``append`` adds one new item to the END of a list. The new item may be of any
data type, including another list.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      letters = ['a', 'b', 'c']

      letters.append('a')
      print(letters)

      letters.append(['l', 'm', 'n', 'o', 'p'])
      print(letters)

   **Output**

   ::

      ['a', 'b', 'c', 'a']
      ['a', 'b', 'c', 'a', ['l', 'm', 'n', 'o', 'p']]

.. admonition:: Note

   To add multiple, separate items to the end of a list:

   #. Use multiple ``append`` statements (possibly in a loop), OR
   #. Use concatenation to add two lists together.

   .. sourcecode:: python
      :linenos:

      letters = ['a', 'b', 'c']
      digits = [0, 1, 2, 3]

      for digit in digits:
         letters.append(digit)   # Each iteration, add a digit to the end of the list.
      
      print(letters)

      letters = letters + ['l', 'm', 'n', 'o', 'p']
      print(letters)

   ::

      ['a', 'b', 'c', 0, 1, 2, 3]
      ['a', 'b', 'c', 0, 1, 2, 3, 'l', 'm', 'n', 'o', 'p']

.. index::
   single: list; insert

.. _list-insert-examples:

``insert`` Examples
-------------------

The general syntax for this method is:

.. sourcecode:: python

   list_name.insert(index, new_value)

``insert`` adds ``new_value`` at the specified ``index`` in the list. The new
element may be of any data type, including another list.

Existing data values that come before ``index`` remain unchanged. Data values
at or after ``index`` all get shifted further down the list.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      languages = ['Python', 'JavaScript', 'Java', 'C#']

      languages.insert(2, 'Swift')
      print(languages)

   **Output**

   ::

      ['Python', 'JavaScript', 'Swift', 'Java', 'C#']
