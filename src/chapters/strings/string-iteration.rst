Iteration with Strings
======================

One of the most common uses of a ``for`` loop is to carry out a task on each
item in a collection. When using a loop with a collection in this way, we say
that the loop *iterates over* the collection.

Iterate by Index or Characters
------------------------------

In the Loops chapter, we learned two ways to
:ref:`iterate over a string <string-iteration>`. The following examples review
those ideas.

.. admonition:: Example

   One way to iterate over a string is to use the index values for each
   character. The following program prints each of the characters of the string
   ``'LaunchCode'`` on a separate line.
   
   Run the code to see the output, then complete the *Try It* suggestions.

   .. replit:: Python
      :slug: StringIterationExample
      :linenos:

      name = 'LaunchCode'

      for index in range(len(name)):
         print(name[index])

   Since ``len(name)`` is 10, the loop executes once for each of the values 0 to
   9, assigning them in turn to the loop variable ``index``.

   The loop body, ``print(name[index])``, prints one of the characters from
   ``name`` (``name[0]`` through ``name[9]`` for ``'LaunchCode'``).

   **Try It!**

   #. Replace the string ``'LaunchCode'`` with your name. Note how using
      ``len(name)`` as the argument inside ``range`` makes the loop run the
      proper number of times, regardless of the string.
   #. Use ``range(start, stop, step)`` to print every third character from
      ``name``.
   #. Loop through the string using *negative* index values. Run the program
      with ``range(-1, -len(range), -1)``. How does the output change?
   #. ``range(-1, -len(range), -1)`` does not quite get all of the letters from
      ``name``. Modify the ``start, stop, step`` values as needed to print all
      of the characters.

Since a string is simply a sequence of characters, Python gives us a way to
automatically iterate over those characters.

.. admonition:: Example
   
   Run the following code to see the output, then complete the *Try It*
   suggestions.

   .. replit:: Python
      :slug: StringIterationExampleChars
      :linenos:

      fruit = 'Bananas'
      fruit_copy = ''

      for char in fruit:
         fruit_copy += char
         print(char, fruit_copy)

   The loop variable ``char`` is automatically reassigned each character in the
   string stored by ``fruit``. This approach is called *iteration by item*.

   We also see an example of the accumulator pattern. The program reassigns a
   new, longer string to ``fruit_copy`` each iteration.
   
   Note that *iteration by item* moves through a collection from left to right.
   If we want to move from right to left, we must use the index values.

   **Try It!**

   #. Replace ``fruit_copy += char`` with
      ``fruit_copy = char.upper() + fruit_copy``. What happens to the output?
   #. Replace ``print(char, fruit_copy)`` with
      ``print(char, fruit.count(char))``. Run the program to see the output.
   #. Use a template literal and ``format()`` to print a more readable message
      each iteration. Something like, ``'Bananas' contains 3 'a' character(s).``
      The output should change each time the loop repeats.

Check Your Understanding
------------------------

.. admonition:: Question

   Given the following code, which character is printed during the *fifth*
   iteration?

   .. sourcecode:: Python
      :linenos:

      text = 'Hello, World!'

      for index in range(len(text)):
         print(text[index])
      
   a. ``'l'``
   b. ``'o'``
   c. ``','``
   d. ``' '``

.. Answer = b

.. admonition:: Question

   Given the following code, which character is printed during the *fifth*
   iteration?

   .. sourcecode:: Python
      :linenos:

      text = 'Hello, World!'

      for char in text:
         print(char)

   a. ``'l'``
   b. ``'o'``
   c. ``','``
   d. ``' '``

.. Answer = b

.. admonition:: Question

   Given the string ``my_dream_car = 'Tesla'``, which of the following will
   loop backwards through all of the characters in the string? Select ALL
   options that work.

   a. ``for index in range(len(my_dream_car)):``
   b. ``for index in range(-1, -len(my_dream_car), -1):``
   c. ``for index in range(len(my_dream_car)-1, -1, -1):``
   d. ``for index in range(-1, -len(my_dream_car)-1, -1):``
   e. ``for char in my_dream_car:``
   f. ``for char in -my_dream_car:``

.. Answers = c & d

