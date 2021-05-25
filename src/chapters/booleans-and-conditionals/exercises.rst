Exercises: Booleans and Conditionals
====================================

If your teacher added you to a :ref:`Trinket course <trinket-course-assignments>`, complete the exercises
there.

Otherwise, use the links below to code in your own free Replit or Trinket account.

Part A: Basic Selection
-----------------------

If you are NOT assigned to a Trinket course, follow one of
these links for the Part A starter code:

#. `repl.it starter <https://repl.it/@launchcode/Conditional-Exercises-Part-A-1>`__
#. `Trinket starter <https://trinket.io/python/a25b2ff397>`__

``if`` Only
^^^^^^^^^^^

Prompt the user to enter a word and store the result in ``user_entry``:

.. sourcecode:: python

   user_entry = input('Enter a word: ')

#. Use a conditional to check the length of the word. If longer than 5
   characters, print, ``"___ is longer than 5 characters."`` Otherwise, print
   nothing. (Note: Fill in the blank with the value of ``user_entry``).

Binary Selection
^^^^^^^^^^^^^^^^

Prompt the user to enter a number:

.. sourcecode:: python

   num_entry = int(input('Enter a number larger than 100: '))

2. Check if ``num_entry`` is 100 or larger. If so, print, ``"Valid entry!"``
   Else print, ``"Number too small."``

The ``in`` keyword can be used as another comparison operator.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      print('ana' in 'banana')
      print('z' in 'apple')

   **Console Output**

   ::

      True
      False

   The string ``ana`` is present within ``banana``, while there is no
   ``z`` character within ``apple``.

3. Prompt the user to enter a lowercase letter. Use the ``in`` operator to
   check if the letter is a vowel (e.g. in the string ``aeiou``). If so, print,
   ``"___ is a vowel."`` Else, print, ``"___ is NOT a vowel."``
#. What happens if the user enters a capital letter instead of lowercase?
   Refactor your code for problem 3 so that it works for both capital and
   lowercase vowels!

Part B: Logical Operators
-------------------------

Use the logical ``and``, ``or``, and ``not`` operators in the following
exercises. Once again, if you are not assigned Trinket course, 
access the Part B starter code here: `repl.it <https://repl.it/@launchcode/Conditional-Exercises-Part-B-1>`__
or `Trinket <https://trinket.io/python/923476a25b>`__.

#. Given an integer, check to see if the number is even and divisible by 5.
   Print an appropriate message depending on the result.

#. Given a string, print, ``"___ is a really long word!"`` if the string is
   longer than 9 characters and does NOT contain a space. Otherwise, print,
   ``"___ is either short, or it contains multiple words."`` Fill in the blank
   with the original string.

#. Refactor the following code to check if ``letter`` is NOT in the string
   ``'BCDFGHJKLMNPQRSTVWXYZ'`` or is a lowercase vowel. How does making this
   change affect the ``if/else`` code blocks?

   .. sourcecode:: python
      :linenos:

      letter = 'A'
      cap_consonants = 'BCDFGHJKLMNPQRSTVWXYZ'
      vowels = 'aeiou'

      if letter in cap_consonants or letter in vowels:
         print("'" + letter + "'", "is either a lowercase vowel OR a capital consonant.")
      else:
         print("Pick a capital consonant or a lowercase vowel.")

#. If ``num = 5``, indicate whether each of following expressions returns
   ``True`` or ``False``.

   .. sourcecode:: python
      :linenos:

      num >= 0 and num*2 <= 50 and num%2 == 0
      num >= 0 or num*2 <= 50 or num%2 == 0
      num >= 0 and num*2 <= 50 or num%2 == 0
      num >= 0 or num*2 <= 50 and num%2 == 0
      not num < 0 and num%3 != 0
      not (num%3 == 0 or num*4 >= 20)

Part C: Chained Conditionals
----------------------------

Use this starter code for Parts C and D: `repl.it <https://repl.it/@launchcode/Conditional-Exercises-Parts-C-and-D>`__
or `Trinket <https://trinket.io/python/014054b0a7?showInstructions=true>`__.

#. For ``if/elif/else`` statements, the *order* of the checks is important.
   The following code should determine if a number is divisible by 2, 3, both
   or neither, but as written it does not behave as we want. Rearrange the
   order of the ``if``, ``elif``, and ``else`` code blocks as needed to give
   the desired results.

   .. sourcecode:: python
      :linenos:

      num = 6 # Try the values 10, 15, and 7 as well.

      if num%2 == 0:
         print(num, "is divisible by 2.")
      elif num%3 == 0:
         print(num, "is divisible by 3.")
      elif num%2 == 0 and num%3 == 0:
         print(num, "is divisible by 2 and 3.")
      else:
         print(num, "is NOT divisible by 2 or 3.")

   For ``num = 6``, the output should be ``'6 is divisible by 2 and 3.'``

#. Given the score on an exam, use a chained conditional to assign it the
   proper letter grade. Assume a standard 10-point range for each letter (A =
   100 - 90, B = 89 - 80, C = 79 - 70, etc.). Print the results as
   ``___% = ___``. Fill in the first blank with the score and the second blank
   with the letter grade.
#. Write code to help you pick an activity based on the current weather.
   Consider two variables, one for temperature (``hot`` or ``cold``) and one
   for how wet it is (``rainy`` or ``dry``). If the weather is hot and rainy,
   your code should tell you to watch Netflix. For hot and dry conditions, it
   should tell you to go swimming. If cold and rainy, it should tell you to
   get under a blanket and read. If it is cold and dry, it should tell you to
   hang out with a friend.

Part D: Nested Conditionals
---------------------------

4. Ask the user for their lunch selection - ``burger`` or ``salad``. If they
   choose ``salad``, ask them for a dressing option (``ranch`` or ``italian``).
   If they choose ``burger`` ask them if they want cheese (``yes`` or ``no``).
   Print out their final order.
#. Each option has a different price. Add a ``cost`` variable to your code and
   calculate the bill for the lunch order. Include this in the print
   statement.
#. Assume you want to add a drink question for the customer. Where would be the
   BEST place to ask this question? EXPLAIN your reasoning for your choice.

   a. Inside the nested statements before the cheese/dressing questions.
   b. Inside the nested statements after the cheese/dressing question.
   c. As a separate conditional outside of the nested statements.
