Lists Are Like Strings
======================

Besides being ordered collections, Python lists share other similarities with strings.

List Length
-----------

.. index::
   single: list; length

The ``len()`` function also returns the length of a list (the number of elements in the list).

.. admonition:: Example

   .. sourcecode:: Python
      :linenos:

      letters = ['a', 'b', 'c', 'x', 'y', 'z']

      print("The list {0} has {1} elements.".format(letters, len(letters))
   
   **Console Output**

   ::

      The list ['a', 'b', 'c', 'x', 'y', 'z'] has 6 elements.

   In line 3, ``len(letters)`` returns the number of items stored in the
   ``letters`` list.

Note that the statement ``print(letters[len(letters)])`` will throw an *index
out of range* error. Since index values start at 0, the last element in any
list will always have a value of ``len(list_name) - 1``.

.. _concatenating-lists:

Combining Lists
---------------

Just like strings, we can use the ``+`` and ``*`` operators for *concatenation*
and *repetition*. Concatenation combines different lists to create one new,
longer list. Repetition makes multiple copies of the same elements within a
single list.

.. admonition:: Try It!

   Experiment with using different operators on lists. Take notes about the
   results you see.

   #. Does order matter?  Print ``first_list + second_list`` vs. 
      ``second_list + first_list``, and then write down your answer.
   #. Does the ``+`` operator change the original list? To check, print
      ``first_list`` again after your code from step 1.
   #. Try printing ``first_list + 13`` vs. ``first_list + [13]``. What happens?
   #. Can we subtract two lists? Try printing ``first_list - second_list``.
   #. What does the ``*`` operator do to a list? Try printing
      ``second_list * 3``.
   #. Does the ``*`` operator change the original list? To check, print
      ``second_list`` again after your code from step 5.

   .. replit:: Python
      :slug: ListConcatenation
      :linenos:

      # Follow the instructions to see how the '+' and '*' operators affect lists.
      first_list = [3, 7, 5, 1, 7]
      second_list = [6, 3, 9]

      # Add your print statements here:

``in`` and ``not in``
---------------------

Just like strings, we can use the ``in`` and ``not in`` operators to check if a
specific value is present in a list. The operators return ``True`` or ``False``
depending on if the value matches an element.

.. _in-not-in-editor:

.. admonition:: Try It!

   Run this program to see the results returned by the ``in`` and ``not in``
   operators.

   .. replit:: Python
      :slug: InAndNotInList
      :linenos: 

      fruit = ["apple", "orange", "banana", "cherry", "tomato", "bell pepper"]

      print('apple' in fruit)       # 'apple' is an element in the list.
      print('pear' in fruit)        # 'pear' is NOT in the list.
      print('nana' in fruit)        # The string 'nana' is NOT an element in the list.
      print('carrot' not in fruit)  # 'carrot' is missing from the list, so 'not in' returns True.

   Note that even though the substring ``'nana'`` is present in ``'banana'``,
   the result of line 5 is still ``False``. In this case, the ``in`` operator
   checks if the string ``'nana'`` is its own element in ``fruit``. To check if
   ``'nana'`` is a smaller piece of each element requires more code.

.. _slicing-lists:

List Slices
-----------

.. index::
   single: list; slice

Just like strings, we can return a *slice* (several elements) from a list.
Taking a slice creates a new list, and the syntax should be familiar:

.. sourcecode:: Python

   list_name[start_index : end_index]

The new list contains the elements from ``start_index`` up to but NOT including
``end_index``. If we leave out ``start_index``, the slice starts at the
beginning of the list. If we leave out ``end_index``, the slice continues to
the end of the list.

The index values in the new list begin at 0.

.. admonition:: Example

   .. sourcecode:: Python
      :linenos:

      original_list = [2, 4, 6, 8, 10, 12, 14]
      
      new_list = original_list[2:5]

      print(new_list, 'vs.', original_list)
      print(new_list[0])
      print(original_list[:3])
      print(original_list[3:])

   **Console Output**

   ::

      [6, 8, 10] vs. [2, 4, 6, 8, 10, 12, 14]
      6
      [2, 4, 6]
      [8, 10, 12, 14]

Try It!
^^^^^^^

In the :ref:`(in/not in) Replit above <in-not-in-editor>`, add slices to check
only a portion of the ``fruit`` list (e.g. ``print("apple" in fruit[2:4])``).

Check Your Understanding
------------------------

.. admonition:: Question

   What is printed by the following code?

   .. sourcecode:: Python
      :linenos:

      a_list = [4, 2, 8, 6, 5, 4]
      print(a_list[3])

   a. 2
   b. 8
   c. 6
   d. 5

.. Answer = c

.. admonition:: Question

   Given ``num_list = [8, 6, 7, 5, 3, 0, 9]``, what does ``num_list[2:5]``
   return?

   a. [7, 5, 3]
   b. [7, 5, 3, 0]
   c. [6, 7, 5]
   d. [6, 7, 5, 3]

.. Answer = a

.. admonition:: Question

   What is printed by the following code?

   .. sourcecode:: Python
      :linenos:

      a_list = [4, 2, 8]
      print(a_list * 2)

   a. [4, 4, 2, 2, 8, 8]
   b. [4, 2, 8, 4, 2, 8]
   c. [8, 4, 16]
   d. The code throws an error.

.. Answer = b

.. admonition:: Question

   Given ``fruit = ["apple", "orange", "banana", "cherry", "tomato", "bell pepper"]``,
   which of the following statements return ``True``? Select ALL that apply.

   a. apples in fruit
   b. pepper in fruit
   c. banana in fruit[:3]
   d. tomato in fruit[1:4]
   e. broccoli not in fruit
   f. orange not in fruit[2:]

.. Answers = c, e, f


