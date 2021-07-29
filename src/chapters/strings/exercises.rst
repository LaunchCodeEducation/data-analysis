.. _strings-exercises:

Exercises: Strings
==================

The exercises have been broken up into three parts. 
There are *five* replit pages with starter code for you to fork. 
Most sections have replit starter code provided.  
You should see links to your starter code below the exercise steps.

Part One: Bracket Notation
--------------------------

Points to Ponder
^^^^^^^^^^^^^^^^

Identify the result for each of the following statements:

*There's no starter code for this one, just try it on your own with old-fashioned pencil and paper!*

1. ``'Characters'[8]``
2. ``"Strings are sequences of characters."[5]``
3. ``len("Wonderful")``
4. ``len("Do spaces count?")``

Bracket Notation Basics
^^^^^^^^^^^^^^^^^^^^^^^

Use bracket notation to:

1. Print a slice of the first 12 characters from
   ``"Strings_are_sequences_of_characters."``
2. Print a slice of the last 12 characters from the same string. You should
   NOT have to count the index values yourself!
3. Print a slice of the middle 12 characters from the same string.

:ref:`Check Your Solutions<strings-exercise-solutions1.2>`



Looping Through a String
^^^^^^^^^^^^^^^^^^^^^^^^

Use index values to loop *backwards* through a string:

1. First, print one letter per line.
2. Next, instead of one letter per line, use the accumulator pattern to build
   up and print the reversed string. For example, if given the string
   ``'good'``, your program prints ``doog``.
3. Finally, use concatenation to print the combination of the original and
   reversed string. For example, given the string ``'tomato'``, your program
   prints ``tomatootamot``. (If you want to be fancy, include the ``|``
   character to make the output look almost like a mirrored image: ``tomato | otamot``). 

:ref:`Check Your Solutions<strings-exercise-solutions1.3>`

.. admonition:: Tip: Starter Code

   `Code it at repl.it <https://replit.com/@launchcode/StringsExercisesPart1-2and3>`__.


Part Two: String Methods and Operations
---------------------------------------

String Methods and Data Types
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The ``len()`` function returns the number of characters in a string. However,
the function will NOT give us the length of an integer. If ``num = 1001``,
then ``len(num)`` throws an error instead of returning ``4``.

1. Use ``str()`` to change ``num`` from an ``int`` to a string data type.
2. Print the length (number of digits) in ``num``.
3. Modify your code to print the number of digits in a ``float`` value (e.g.
   ``num = 123.45`` has 5 digits but a length of 6). The digit count should
   NOT include the decimal point.
4. What if ``num`` could be EITHER an integer or a decimal? Add an ``if/else``
   statement so your code can handle both cases.  (Hint: Consider using the
   ``find()`` method or the ``in`` operator to check if ``num`` contains a
   decimal point).

:ref:`Check Your Solutions<strings-exercise-solutions2.1>`

.. admonition:: Tip: Starter Code

   `Code it at repl.it <https://replit.com/@launchcode/StringsExercisesPart2-1>`__.

Loops, Conditionals, and Strings! Oh my!
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Given ``word = 'bag'``:

1. Set up a loop to iterate through the string of lowercase vowels,
   ``'aeiou'``.
2. Inside the loop, create a new string from ``word``, but with a different
   vowel. Use the ``replace()`` string method.
3. Print the new string.
   
   Properly done, your output should look something like this:

   ::

      bag
      beg
      big
      bog
      bug
   
4. Try other words besides ``'bag'``!

:ref:`Check Your Solutions<strings-exercise-solutions2.2>`

.. admonition:: Tip: Starter Code

   `Code it at repl.it <https://replit.com/@launchcode/StringsExercisesPart2-2>`__.

Method Chaining Fun with DNA
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Consider a string that represents a strand of DNA:
``dna = " TCG-TAC-gaC-TAC-CGT-CAG-ACT-TAa-CcA-GTC-cAt-AGA-GCT    "``. There
are some typos in the string that you need to fix:

1. Use the ``strip()`` method to remove the leading and trailing whitespace,
   and then print the result.
2. Change all of the letters in the DNA string to UPPERCASE and print the
   result.
3. Note that you need to *reassign* the changes back to the ``dna`` variable in order to see them printed. 
   Apply these fixes to your code so that ``print(dna)`` prints the DNA strand in UPPERCASE
   with no whitespace.

4. Let's use string methods to do more work on the same DNA strand:

   a. Use ``replace()`` to remove the sequence ``'GCT'``, and then print the altered
      strand. Don't forget about the extra hyphen!
   b. Look for the sequence ``'CAT'`` with ``find()``. If found print, ``'CAT
      found'``, otherwise print, ``'CAT NOT found'``.
   c. Use ``count()`` to find the number of hyphens (``-``) in the string, then
      print the number of *genes* (in this case, a gene is a set of 3 letters) in the DNA strand. Note
      that the number of genes will be 1 more than the number of hyphens. 
   d. Finally, use an f-string to print the output
      ``"The DNA string is ___ characters long and contains ___ genes."`` Fill in
      the blanks with the length of the string and the number of genes.

:ref:`Check Your Solutions<strings-exercise-solutions2.3>`

.. admonition:: Tip: Starter Code

   `Code it at repl.it <https://replit.com/@launchcode/StringsExercisesPart2-3and4>`__.

Part Three: String Formatting
-----------------------------

Template Literals
^^^^^^^^^^^^^^^^^


Assign your favorite, school-appropriate number and word to two variables.
   
1. Use ``format()`` and index values to print the string,
   ``"Here is my number: ___, and here is my word: ___, and here is my
   number again: ___."``
2. Print the string, ``"Here is my word 3 times: ___/___/___, and here is my
   number squared: ___."``


:ref:`Check Your Solutions<strings-exercise-solutions3.1>`

.. admonition:: Tip: Starter Code

   `Code it at repl.it <https://replit.com/@launchcode/StringsExercisesPart3-1>`__.

Debugging Practice
^^^^^^^^^^^^^^^^^^



*No starter code for this one.*

The following code sample works, but it can be improved.

1. Assuming that ``advice`` remains a string, when will the code produce the
   wrong output?
2. Why will the code do this?
3. What should the programmer do to fix the code?

.. sourcecode:: python
   :linenos:

   advice = "Don't Panic"

   output = "The text, '{0}' contains {1} characters."

   print(output.format("Don't Panic", 11))

**Console Output**

::

   The text, 'Don't Panic' contains 11 characters.

:ref:`Check Your Solutions<strings-exercise-solutions3.2>`

Submitting Your work
--------------------

Phew! That was a lot of work and a lot of replits.  
Quick completion (sanity) check: You should have *five* replit pages once you finished the Template Literal exercises.
