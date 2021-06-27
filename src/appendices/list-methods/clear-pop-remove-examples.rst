Removing Elements From a List
=============================

The ``clear``, ``pop``, and ``remove`` list methods *mutate* (change) the
original list.

.. index::
   single: list; clear

.. _list-clear-examples:

``clear`` Example
-----------------

The general syntax for this method is:

.. sourcecode:: python

   list_name.clear()

``clear`` removes all elements from a list. The list still exists, but it is
empty.

No arguments go inside the ``()``.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      mt_list = ['This', 'list', 'of', 9, 'elements', 'will', 'soon', 'be', 'empty!']

      mt_list.clear()
      print(mt_list)
      print(len(mt_list))  # Print the length of the list

   **Output**

   ::

      []
      0

.. index::
   single: list; pop

.. _list-pop-examples:

``pop`` Examples
----------------

The general syntax for this method is:

.. sourcecode:: python

   list_name.pop(index)

``pop`` removes the element at ``index`` from the list. However, providing an
``index`` value is *optional*. If left blank, ``pop()`` removes the last item
from the list.

In addition to *removing* an item from the list, ``pop`` also *returns* that
value. This means ``list_name.pop(index)`` can be printed or assigned to a
variable.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      a_list = [100, 99, 98, 97, 96]

      a_list.pop(2)  # Removes and returns the element at index 2
      print(a_list)

      removed_element = a_list.pop()  # Removes and returns the last element
      print(removed_element)
      print(a_list)

   **Output**

   ::

      [100, 99, 97, 96]
      96
      [100, 99, 97]

.. index::
   single: list; remove

.. _list-remove-examples:

``remove`` Examples
-------------------

The general syntax for ``remove`` is:

.. sourcecode:: python

   list_name.remove(value)

This method removes the FIRST element in a list that matches ``value``.

``value`` may be of any data type.

If Python does not find ``value`` inside the list, it throws an error, and the
program will likely crash.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      b_list = [89, 88, 87, 88, 89, 80, 88]

      b_list.remove(88)  # Removes the first 88 from the list (index 1).
      print(b_list)

      b_list.remove(77)  # Throws an error.
      print(b_list)

   **Output**

   ::

      [89, 87, 88, 89, 80, 88]
      Line 6:
         b_list.remove(77) # Throws an error.
         ValueError: list.remove(x): x not in list      

To remove ALL elements that match ``value``, we must repeatedly call the
method. One approach is to use a ``while`` loop.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      b_list = [89, 88, 87, 88, 89, 80, 88]

      while b_list.count(88) > 0: # The condition checks if there are still values to remove.
         b_list.remove(88)
         print(b_list)

   **Output**

   ::

      [89, 87, 88, 89, 80, 88]
      [89, 87, 89, 80, 88]
      [89, 87, 89, 80]
