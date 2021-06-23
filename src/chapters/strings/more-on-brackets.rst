Taking a Slice
==============

.. index:: ! substring, ! slice

In addition to accessing single characters in a string, we can also use bracket
notation to return multiple characters. This smaller set of characters is
called a **substring** of the original.

A substring is also called a **slice** of the original string. Selecting a
slice is similar to selecting a character, and the syntax is:

.. sourcecode:: Python

   some_string[start_index : end_index]

With this format, Python returns all of the characters from the ``start_index``
value up to but NOT including the ``end_index`` value.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      alphabet = 'abcdefghijklmnopqrstuvwxyz'
      substring = alphabet[2:5]

      print(substring)

   **Console Output**

   ::

      cde

   Since we start counting at 0, the character at index value 2 is ``'c'``,
   and the character at index 5 is ``'f'``. However, note that ``'f'`` is
   NOT included in the slice.

If we leave out the first index (before the colon), the slice starts at the
beginning of the string. If we leave out the second index, the slice goes to
the end of the string.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      fruit = "cucumber"
      print(fruit[:3])
      print(fruit[3:])

   **Console Output**

   ::

      cuc
      umber
   
   What do you think ``fruit[:]`` means?

   How about ``fruit[-5:-2]``?

Saving Substrings
-----------------

In the examples above, we simply print a substring to the
console, like ``print(fruit[:3])``. This works because when we use brackets to
return part of a string, we actually *create a new string*.
This new string is a piece of data, and we can perform operations on it like any other string. The
expression ``fruit[:3]`` returns the string ``'cuc'``, so the ``print`` function
displays that data in the console. If we want to use the string ``'cuc'`` again, we will need
to take another slice from ``fruit``, or save the string in a new variable.

Instead of creating, using, then losing a new string, we can assign it to a
variable whenever we use bracket notation.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      vegetable = "carrot"
      top_half = vegetable[0:3]
      end_piece = vegetable[-1]

      print(top_half, end_piece, vegetable)
   
   **Console Output**

   ::
   
      car t carrot

By assigning the substrings ``'car'`` and ``'t'`` to variables, we can use
those strings elsewhere in the program.

.. admonition:: Note

   **BIG IDEA**!!! Notice that taking two slices from the string ``'carrot'``
   did NOT change the string itself. We will explore this idea in the next
   section.

Check Your Understanding
------------------------

.. admonition:: Question

   Given ``language = 'Python'``, what does ``language[1:5]`` return?

   a. ``"Pyth"``
   b. ``"Pyt"``
   c. ``"yth"``
   d. ``"ytho"``

.. Answer: d


