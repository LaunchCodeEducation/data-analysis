.. _dictionary-copy-example:

Cloning a Dictionary
====================

.. index::
   single: dictionary; copy()

As we saw in the :ref:`cloning lists section <cloning-lists>`, if we code
something like ``list_b = list_a``, we create two variables that point to the
*SAME* memory location. The same list has two different names. Anything we
do to ``list_a`` also happens to ``list_b``, since the two labels refer to the
same set of data.

We call giving two names to the same data *aliasing*, and this can happen with
dictionaries as well.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      opposites = {'up' : 'down', 'right' : 'wrong', 'hot' : 'cold'}
      other = opposites

      opposites['right'] = 'left'
      print(opposites)
      print(other)

   **Console Output**

   ::

      {'up' : 'down', 'right' : 'left', 'hot' : 'cold'}
      {'up' : 'down', 'right' : 'left', 'hot' : 'cold'}
   
   When we perform an action on the ``opposites`` dictionary, we see the
   effects when we use the ``other`` alias.

Create an Independent Copy
--------------------------

If we want to modify a dictionary but keep the original intact, we use the
``copy()`` method.  The general syntax is:

.. sourcecode:: python

   dict_copy = original_dict.copy()

The ``copy()`` method creates a new dictionary in a new memory location and
assigns it to the ``dict_copy`` variable. Changes made to the original
dictionary will NOT affect the copy, and vice versa.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      opposites = {'up' : 'down', 'right' : 'wrong', 'hot' : 'cold'}
      other = opposites.copy()

      opposites['right'] = 'left'
      other.pop('up')
      print(opposites)
      print(other)

   **Console Output**

   ::

      {'up' : 'down', 'right' : 'left', 'hot' : 'cold'}
      {'right' : 'wrong', 'hot' : 'cold'}
