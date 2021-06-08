Chained Conditionals
====================

.. index::
   single: conditional; chained

A **chained conditional** consists of a series of checks that are evaluated one
after the other. If one check in the series evaluates to ``True``, then all of
the following checks are ignored.

``elif`` Statements
-------------------

.. index:: ! elif

``If/else`` statements provide two alternative paths. A single condition
determines which path to follow. We can build more complex conditionals using
an **elif** clause. ``elif`` stands for *else if*, and it allows us to include
more conditions and code blocks. This leads to more branches for our code to
follow.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      num = 10
      other_num = 20

      if num > other_num:
         print(num, "is greater than", other_num)
      elif num < other_num:
         print(num, "is less than", other_num)
      else:
         print(num, "is equal to", other_num)

   **Console Output**

   ::

      10 is less than 20

**Summary:**

#. Line 4 begins the chained conditional. The boolean expression ``num > other_num``
   returns ``False``, since 10 is not greater than 20. This causes line 5 to be
   skipped.
#. Line 6 contains the ``elif`` statement. The boolean expression
   ``num < other_num`` returns ``True``, since 10 is less than 20. This
   triggers line 7.
#. The code block for the ``else`` clause (line 9) is skipped, because one of
   the conditions above it was true.

.. admonition:: Note

   Just like with a simple ``if`` statement, the ``else`` clause is also optional
   for ``elif`` statements. In the example above, removing lines 8 & 9 will
   not break anything. However, the program will not print anything when
   ``num`` equals ``other_num``, since the ``if`` and ``elif`` conditions both
   return ``False``.

Multiple ``elif`` Statements
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

We can include more than one ``elif`` statement within a conditional. For
example, the following code sample prints different messages depending on the
first character in a string.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      character = 'P'
      lowercase = 'abcdefghijklmnopqrstuvwxyz'
      uppercase = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
      digits = '0123456789'

      if character in lowercase:
         print(character, 'is a lowercase letter.')
      elif character in uppercase:
         print(character, 'is an UPPERCASE letter.')
      elif character in digits:
         print(character, 'is a number.')
      else:
         print('&**%#!', character, 'is a punctuation mark or a space.')

We can easily add more ``elif`` statements to the conditional if we need to
perform more checks. This gives us a huge amount of flexibility if we decide
to modify the program later.

Here are some rules for building ``if/elif/else`` statements:

#. Order is important. The ``if`` statement comes first, then the ``elif``
   statements, and finally the ``else``.
#. The ``if`` statement and code block are required. The ``elif`` and ``else``
   clauses are optional.
#. Conditionals contain only ONE ``if`` statement and only ONE ``else``
   (if used).
#. Multiple ``elif`` statements are allowed after the ``if`` statement, but
   they must come before the ``else`` clause.

No matter how long we make a chained conditional, *no more than one* of the
code blocks will run.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      num = 10;
      other_num = 20;

      if num > other_num:
         print(num, "is greater than", other_num)
      elif num < other_num:
         print(num, "is less than", other_num)
      elif num % 5 == 0:
         print(num, "is divisible by 5")
      elif num % 2 == 0:
         print(num, "is even")

   **Console Output**

   ::

      10 is less than 20

Even though both of the conditions ``num % 5 == 0`` and ``num % 2 == 0``
evaluate to ``True``, neither line 9 nor 11 runs. Since line 6 is satisfied
first, the rest of the conditional is skipped.

Nested vs. Chained Conditionals
-------------------------------

On the previous page, we used a nested conditional to print different outputs
based on the length of a word. We can accomplish the same result with a
chained conditional.

.. admonition:: Example

   Here is the nested conditional again:

   .. sourcecode:: python
      :linenos:

      word = input('Please enter a word: ')

      if len(word) == 4:
         print("What did your mom tell you about using 4-letter words?")
      else:
         if len(word) < 4:
            print("You can think of a longer word than that!")
         else:
            print("Excellent word!")

   The following chained conditional produces the same result:

   .. sourcecode:: python
      :linenos:

      word = input('Please enter a word: ')

      if len(word) == 4:
         print("What did your mom tell you about using 4-letter words?")
      elif len(word) < 4:
         print("You can think of a longer word than that!")
      else:
         print("Excellent word!")

Often, you can use a nested conditional or a chained conditional to solve the
same problem. Which one you choose depends on your personal preference, but
you should always use the option that makes your code easier for others to
read.

.. admonition:: Example

   Nesting one conditional inside of another performs a *check within a check*,
   and we can do this any number of times.

   .. sourcecode:: python
      :linenos:

      if condition_1:
         # code here

         if condition_2:
            # code here

            if condition_3:
               # code here
            else:
               # code here

         else:
            # code here

      else:
         # code here

Perhaps you see the problem with nesting more than once or twice. The code
quickly gets very difficult to read and follow.

Even though we COULD code a check within a check within a check within a check
within a check (etc.), we really SHOULDN'T. In most instances, we can
make our code more readable by using chained conditionals and/or logical
operators in place of nested conditionals.

Check Your Understanding
------------------------

.. admonition:: Question

   What does the following code print?

   .. sourcecode:: python
      :linenos:

      num = 8

      if num % 2 == 0:
         print("Launch")
      elif num > 5:
         print("Code")
      else:
         print("LaunchCode")

      a. ``Launch``
      b. ``Code``
      c. ``Launch Code``
      d. ``LaunchCode``

.. Answer = a

.. admonition:: Question

   Examine this nested conditional:

   .. sourcecode:: python
      :linenos:

      num = -10
      if num < 0:
         print("The negative number", num, "is not valid here.")
      else:
         if num > 0:
            print(num, "is a positive number")
         else:
            print(num, "is 0")

   Which of the following code blocks gives the same result?

   a. .. sourcecode:: python
         :lineno-start: 2

         if num < 0:
            print("The negative number", num, "is not valid here.")
         else num > 0:
            print(num, "is a positive number")
         else:
            print(num, "is 0")
   b. .. sourcecode:: python
         :lineno-start: 2

         if num < 0:
            print("The negative number", num, "is not valid here.")
         elif num > 0:
            print(num, "is a positive number")
         else:
            print(num, "is 0")
   c. .. sourcecode:: python
         :lineno-start: 2

         if num < 0:
            print("The negative number", num, "is not valid here.")
         if num > 0:
            print(num, "is a positive number")
         else:
            print(num, "is 0")

.. Answer = b
