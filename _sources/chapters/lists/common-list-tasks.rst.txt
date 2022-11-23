Common List Tasks
=================

Lists provide a very flexible tool for storing and organizing data. As you use
them again and again, you will often find yourself running the same type of
task.

Let's take a moment to look at some routine list techniques.

Switching Two Elements
----------------------

The ``sort`` and ``reverse`` methods reorder all of the elements in a list.
However, sometimes we only need to swap the positions of two items.

Let's take a look at the long way first, so you can appreciate the shortcut
that much more.

.. admonition:: Example

   Swapping two elements the long way. We need to use a variable to temporarily
   store one of the values we want to swap.

   .. sourcecode:: python
      :linenos:

      my_list = ['r', 'a', 't']

      temp_value = my_list[0]    # Assigns the value 'r' to temp_value 
      my_list[0] = my_list[2]    # Changes ['r', 'a', 't'] to ['t', 'a', 't']
      my_list[2] = temp_value    # Finishes the exchange

      print(my_list)

   **Console Output**

   ::

      ['t', 'a', 'r']
   
   #. Line 3 assigns the value at index 0 (``'r'``) to the ``temp_value``
      variable.
   #. Line 4 assigns the value at index 2 to index 0. Printing ``my_list`` at
      this point would return ``['t', 'a', 't']``.
   #. Line 5 assigns ``temp_value`` to index 2.

Switching the order of two list elements is so common that Python gives us a
shortcut.

.. admonition:: Example

   Swapping two elements the short way. 

   .. sourcecode:: python
      :linenos:

      my_list = ['r', 'a', 't']

      my_list[0], my_list[2] = my_list[2], my_list[0]

      print(my_list)

   **Console Output**

   ::

      ['t', 'a', 'r']

The idea behind the shortcut is that, if we have two list elements---``a`` and
``b``---then the syntax:

::

   a, b = b, a

switches the positions of the two elements inside the list.

.. _list-accumulation:

Accumulating List Elements
--------------------------

Just like strings, we can use the
:ref:`accumulator pattern <accumulator-pattern>` to add items to a list.
Since the ``append`` method only adds one element at a time, placing the
statement inside a loop allows us to continually increase the size of a list.

As we did when keeping a running total, we need to define an accumulator
variable, but in this case it will be assigned an empty list, ``[]``.

.. admonition:: Example

   Let's begin by adding even numbers to an empty list:

   .. sourcecode:: python
      :linenos:

      evens = []     # evens is the accumulator variable

      for num in range(0, 21, 2):  # num takes the values 0, 2, 4...20.
         evens.append(num)         # Add the value of num to the end of the list.

      print(evens)

   **Console Output**

   ::

      [0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20]

We can also use the accumulator pattern to add selected elements from one list
to another.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      words = ['It', 'was', 'a', 'bright', 'cold', 'night', 'in', 'April', 'and', 'all', 'the', 'clocks', 'were', 'striking', 'thirteen']   
      a_words = []        # Accumulator list

      for word in words:            # word takes the value of each element from words.
         if word[0].lower() == 'a': # True if word starts with 'a' or 'A'.
            a_words.append(word)    # Add word to the list.

      print(a_words)

   **Console Output**

   ::

      ['a', 'April', 'and', 'all']

.. admonition:: Note

   One benefit of using the accumulator pattern is that it preserves the
   original list.

Multiple List Options
^^^^^^^^^^^^^^^^^^^^^

In the same accumulator loop, we can use a conditional to decide which list
receives a value.

.. admonition:: Example

   Let's divide a list of mixed data types into strings and integers:

   .. sourcecode:: python
      :linenos:

      mixed_types = [5, 7, 3.14, 'rutabaga', 'integer', True]
      integers = []
      strings = []

      for item in mixed_types:
         if type(item) == str:      # Check if item is a string data type.
            strings.append(item)
         elif type(item) == int:    # Check if item is an int data type.
            integers.append(item)
      
      print(mixed_types)
      print(integers)
      print(strings)
   
   **Console Output**

   ::

      [5, 7, 3.14, 'rutabaga', 'integer', True]
      [5, 7]
      ['rutabaga', 'integer']

   Note that the values ``3.14`` and ``True`` are not placed into either
   list, since they are of the ``float`` and ``bool`` data types,
   respectively.

   We could easily extend the ``if/elif`` block to deal with other data types.

Try It!
^^^^^^^

In the code editor below, practice using the accumulator pattern to add
selected elements to different lists.

.. admonition:: Try It!

   Assign elements from the ``strings`` list into either ``vowel_start``,
   ``digit_start``, or ``other_start``.

   #. In line 7, use a ``for`` statement to loop through ``strings`` by
      element.

      .. sourcecode:: python

         for item in strings:

   #. In line 8, use an ``if`` statement to check if ``item`` starts with a
      vowel. If so, append ``item`` to the ``vowel_start`` list.
   #. Add an ``elif`` statement to check if ``item`` starts with a digit (0-9).
      If so, append ``item`` to ``digit_start``.
   #. Add an ``else`` block to deal with strings that do NOT start with a digit
      or a vowel.
   #. Print the lists after the loop to check your work.

   .. replit:: python
      :slug: AccumulatorList
      :linenos:

      strings = ['apple', 'banana', '1-to-1', '@launchcode', 'everyone can code', ':-)', '4EVR']
      vowel_start = []
      digit_start = []
      other_start = []

      # Add your loop here:


   **Expected Results**

   ::

      vowel_start: ['apple', 'everyone can code']
      digit_start: ['1-to-1', '4EVR']
      other_start: ['banana', '@launchcode', ':-)']

Finding Max and Min
-------------------

Often, we want to find the largest or smallest value from the elements in a
list. We can accomplish this two different ways.

#. Sorting a list arranges the elements from the smallest to largest value.
   The maximum (or minimum) value can then be accessed with bracket notation.

   .. admonition:: Example

      .. sourcecode:: python
         :linenos:

         numbers = [42, 27, 30, 46, -36, 30, -28, 53, 53, 32]
         output = "Minimum = {0}, Maximum = {1}"

         numbers.sort()
         print(numbers)
         print(output.format(numbers[0], numbers[-1]))
         # Index 0 is the first element in the list, and index -1 is the last.

      **Console Output**

      ::

         [-36, -28, 27, 30, 30, 32, 42, 46, 53, 53]
         Minimum = -36, Maximum = 53

#. Python also has two functions, ``max()`` and ``min()``, that return the
   largest and smallest values from a collection.

   .. admonition:: Example

      .. sourcecode:: python
         :linenos:

         numbers = [42, 27, 30, 46, -36, 30, -28, 53, 53, 32]
         output = "Minimum = {0}, Maximum = {1}"

         largest = max(numbers)
         smallest = min(numbers)
         print(numbers)
         print(output.format(smallest, largest))

      **Console Output**

      ::

         [42, 27, 30, 46, -36, 30, -28, 53, 53, 32]
         Minimum = -36, Maximum = 53

      Since the ``max`` and ``min`` functions *return* a value, we could easily
      use the expressions inside ``format``.

      .. sourcecode:: python
         :lineno-start: 4

         print(numbers)
         print(output.format(min(numbers), max(numbers)))

.. admonition:: Note

   Finding the maximum and minimum values also works with strings.

   ``max(['apple', 'bear', 'zebra', 'display'])`` returns ``'zebra'``, and
   ``min('telescope')`` returns ``'c'``.

Check Your Understanding
------------------------

.. admonition:: Question

   What does the following program print?

   .. sourcecode:: python
      :linenos:

      my_list = []

      for num in range(7):
         if num%2 == 0:
            my_list.append(num)
      
      print(my_list)

   a. []
   b. [0, 1, 2, 3, 4, 5, 6]
   c. [0, 2, 4, 6]
   d. [1, 3, 5]

.. Answer = c

.. admonition:: Question

   What does the following program print?

   .. sourcecode:: python
      :linenos:

      my_list = [8, 2, 7, 4, 10]

      my_list[2], my_list[4] = my_list[4], my_list[2]
      
      print(my_list)

   a. [8, 2, 7, 4, 10]
   b. [8, 4, 7, 2, 10]
   c. [10, 4, 7, 2, 8]
   d. [8, 2, 10, 4, 7]

.. Answer = d

.. admonition:: Question

   What does the following program print?

   .. sourcecode:: python
      :linenos:

      word = 'bookkeeper'
      some_letters = []
      other_letters = []
      
      for char in word:
         if char not in 'aeiou':
            some_letters.append(char)
         else:
            other_letters.append(char)
      
      print(some_letters)

   a. ['b', 'k', 'k', 'p', 'r']
   b. ['o', 'o', 'e', 'e', 'e']
   c. ['bkkpr']
   d. ['ooeee']

.. Answer = a