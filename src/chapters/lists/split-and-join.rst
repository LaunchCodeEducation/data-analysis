``split`` and ``join``
======================

Two of the most useful methods involving lists and strings are the methods
``split`` and ``join``. The ``split`` method applies to strings, and it breaks
a string into a list of words. By default, any number of whitespace characters
is considered a word boundary.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      text = "Do what you can, with what you have, where you are."
      words = text.split()
      print(words)
      print(len(words))

   **Console Output**

   ::

      ['Do', 'what', 'you', 'can,', 'with', 'what', 'you', 'have,', 'where', 'you', 'are.']
      11

.. index:: delimiter

We can place an optional argument, called a **delimiter**, inside the ``()``. The
delimiter sets the characters to use as word boundaries. The following example
uses the string ``se`` as the delimiter:

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      text = "Be yourself. Everyone else is already taken."
      words = text.split('se')
      print(words)
      print(len(words))

   **Console Output**

   ::

      ['Be your', 'lf. Everyone el', ' is already taken.']
      3

Notice that the delimiter does NOT appear in the result.

The opposite of the ``split`` method is ``join``, which is used on a list. The
method takes all of the elements from the list, combines them, and returns a
new string value. To use ``join``, we must give Python a *connector* string to
place between the list elements.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      words = ['Hello', 'how', 'are', 'you?']
      connector = '-'
      new_string = connector.join(words)
      print(new_string)
      print(words)

      print('***'.join(words))
      print(''.join(words))

   **Console Output**

   ::

      Hello-how-are-you?
      ['Hello', 'how', 'are', 'you?']
      Hello***how***are***you?
      Hellohowareyou?

Note that the original list (``words`` in this example) remains unchanged. Also,
we can use the empty string, whitespace characters (like ``' '`` or ``'\n'``)
or multi-character strings as the connector.

Use ``split`` and ``join``
--------------------------

These two methods are SUPER useful, since they allow us to convert between a
mutable data type and an immutable one.

.. admonition:: Try It!

   Let's put together a program that alphabetizes the words in a string.

   #. On line 4, define the ``tools_list`` variable and set it equal to
      ``tools.split()``.
   #. On line 5, print ``tools_list`` and note how each element includes a
      comma as part of the word. Let's fix this.
   #. Inside ``split()`` set the delimiter to be a comma followed by a space
      ``', '``. Rerun the program to verify that ``tools_list`` contains only
      words now.
   #. On line 6, apply the ``sort()`` method to ``tools_list``. Note that you
      do NOT need to assign the sorted list to a variable.
      ``tools_list.sort()`` is all you need.
   #. Print ``tools_list`` again to verify that it is now alphabetized.
   #. Next, set ``sorted_string`` equal to ``''.join(tools_list)``, then print
      ``sorted_string``.
   #. The words in ``sorted_string`` are all squeezed together. Change the
      *connector* string in the ``join`` statement to be something other than
      the empty string. Try connecting the words with a hyphen, a comma, a
      space, and a comma-space to see which one looks best when printed.

   .. replit:: python
      :slug: SplitAndJoin
      :linenos:

      # Follow the given instructions to code a program that produces an alphebetized string.
      tools = "hammer, screwdriver, pliers, drill, clamp"
      sorted_string = ''

   *Question*: Did the program change the original ``tools`` string? What can
   you do to find out?

.. admonition:: Note

   It is possible to alphabetize the string without using lists, but the code
   would be much more complicated. The difficulty comes with figuring out the
   proper order of words in the new string. This requires multiple slices from
   ``tools``, plus conditionals to arrange the words, followed by repeated
   concatenation.

   Placing the words into a list saves us a lot of time and effort.

List Type Conversion
--------------------

Python has a built-in type conversion function called ``list`` that tries to
turn whatever you give it into a list.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      test = list("Crunchy Frog")
      print(test)

   **Console Output**

   ::

      ['C', 'r', 'u', 'n', 'c', 'h', 'y', ' ', 'F', 'r', 'o', 'g']

The string ``"Crunchy Frog"`` gets turned into a list by taking each character
in the string and making it an element in the new list. Note that the ``list``
conversion function only works on data types that consist of smaller pieces.

In general, any *collection* can be turned into a list using this function.

.. _list_reverse-a-string:

For strings, ``list`` produces a different result than the ``split`` method.
``split`` breaks a string into a list of *words*, while ``list`` breaks it into
a list of *characters*.

.. admonition:: Try It!

   In the program below, lines 5 - 7 use the accumulator pattern to reverse the
   characters in ``text``. Let's use the ``list`` function to reverse
   ``other_text``:
   
   #. On line 11, define the ``char_list`` variable and set it equal to
      ``list(other_text)``.
   #. On line 12, print ``char_list`` to verify that the function separated
      ``other_text`` into single characters.
   #. On line 13, apply the ``reverse()`` method to ``char_list``. Note that you
      do NOT need to assign the reversed list to a variable.
      ``char_list.reverse()`` is all you need.
   #. Next, define the variable ``rev_other`` and set it equal to
      ``''.join(char_list)``.
   #. Print ``rev_other``.

   .. replit:: python
      :slug: ListAndJoin
      :linenos:

      text = 'Taco Cat'
      other_text = 'Python ROCKS!'

      # Reverse a string with a loop:
      rev_text = ''
      for char in text:
      rev_text = char + rev_text
      print(rev_text)

      # Reverse a string with list & join:

   Note that the ``print`` statement on line 12 is not needed for this
   technique to work. We just use it so see what the ``list()`` function
   returns.

Check Your Understanding
------------------------

.. admonition:: Question

   What is printed by the following statements?

   .. sourcecode:: python
      :linenos:

      my_name = 'Edgar Allan Poe'
      my_names = my_name.split()
      initials = ''
      for name in my_names:
         initials += name[0]
      print(initials)

   a. Poe
   b. EdgarAllanPoe
   c. EAP
   d. William Shakespeare

.. Answer = c


