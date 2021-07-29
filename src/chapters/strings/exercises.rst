Exercises: Strings
==================

There are three sections to this chapter's exercises. 

Part One: Bracket Notation
--------------------------

**Section 1: Points to Ponder**

Identify the result for each of the following statements:

*There's no starter code for this one, just try it on your own with old-fashioned pencil and paper!*

a. ``'Characters'[8]``
b. ``"Strings are sequences of characters."[5]``
c. ``len("Wonderful")``
d. ``len("Do spaces count?")``

**Section 2:  Bracket Notation Basics** 

Use bracket notation to:

a. Print a slice of the first 12 characters from
   ``"Strings_are_sequences_of_characters."``
b. Print a slice of the last 12 characters from the same string. You should
   NOT have to count the index values yourself!
c. Print a slice of the middle 12 characters from the same string.

**Section 3: Looping Through a String** 

Use index values to loop *backwards* through a string:

a. First, print one letter per line.
b. Next, instead of one letter per line, use the accumulator pattern to build
   up and print the reversed string. For example, if given the string
   ``'good'``, your program prints ``doog``.
c. Finally, use concatenation to print the combination of the original and
   reversed string. For example, given the string ``'tomato'``, your program
   prints ``tomatootamot``. (If you want to be fancy, include the ``|``
   character to make the output look almost like a mirrored image: ``tomato | otamot``). 

.. admonition:: Tip

   `Code sections 2 and 3 at repl.it <https://replit.com/@launchcode/StringsExercisesPart1-2and3>`__.


Part Two: String Methods and Operations
---------------------------------------

**Section 1:  String Methods and Data Types**

The ``len()`` function returns the number of characters in a string. However,
the function will NOT give us the length of an integer. If ``num = 1001``,
then ``len(num)`` throws an error instead of returning ``4``.

a. Use ``str()`` to change ``num`` from an ``int`` to a string data type.
b. Print the length (number of digits) in ``num``.
c. Modify your code to print the number of digits in a ``float`` value (e.g.
   ``num = 123.45`` has 5 digits but a length of 6). The digit count should
   NOT include the decimal point.
d. What if ``num`` could be EITHER an integer or a decimal? Add an ``if/else``
   statement so your code can handle both cases.  (Hint: Consider using the
   ``find()`` method or the ``in`` operator to check if ``num`` contains a
   decimal point).

.. admonition:: Tip

   `Code it at repl.it <https://replit.com/@launchcode/StringsExercisesPart2-1>`__.

**Section 2: Loops, Conditionals, and Strings! Oh my!**

Given ``word = 'bag'``:

a. Set up a loop to iterate through the string of lowercase vowels,
   ``'aeiou'``.
b. Inside the loop, create a new string from ``word``, but with a different
   vowel. Use the ``replace()`` string method.
c. Print the new string.
d. Properly done, your output should look something like this:

   ::

      bag
      beg
      big
      bog
      bug
   
e. Try other words besides ``'bag'``!

.. admonition:: Tip

   `Code it at repl.it <https://replit.com/@launchcode/StringsExercisesPart2-2>`__.

**Section 3: Method Chaining Fun with DNA**

Consider a string that represents a strand of DNA:
``dna = " TCG-TAC-gaC-TAC-CGT-CAG-ACT-TAa-CcA-GTC-cAt-AGA-GCT    "``. There
are some typos in the string that you need to fix:

a. Use the ``strip()`` method to remove the leading and trailing whitespace,
   and then print the result.
b. Change all of the letters in the DNA string to UPPERCASE and print the
   result.
c. Note that you need to *reassign* the changes back to the ``dna`` variable in order to see them printed. 
   Apply these fixes to your code so that ``print(dna)`` prints the DNA strand in UPPERCASE
   with no whitespace.

d. Let's use string methods to do more work on the same DNA strand:

   #. Use ``replace()`` to remove the sequence ``'GCT'``, and then print the altered
      strand. Don't forget about the extra hyphen!
   #. Look for the sequence ``'CAT'`` with ``find()``. If found print, ``'CAT
      found'``, otherwise print, ``'CAT NOT found'``.
   #. Use ``count()`` to find the number of hyphens (``-``) in the string, then
      print the number of *genes* (in this case, a gene is a set of 3 letters) in the DNA strand. Note
      that the number of genes will be 1 more than the number of hyphens. 
   #. Finally, use an f-string to print the output
      ``"The DNA string is ___ characters long and contains ___ genes."`` Fill in
      the blanks with the length of the string and the number of genes.

.. admonition:: Tip

   `Code it at repl.it <https://replit.com/@launchcode/StringsExercisesPart2-3and4>`__.

Part Three: String Formatting
-----------------------------

**Section 1:  Template Literals**

Assign your favorite, school-appropriate number and word to two variables.
   
a. Use ``format()`` and index values to print the string,
   ``"Here is my number: ___, and here is my word: ___, and here is my
   number again: ___."``
b. Print the string, ``"Here is my word 3 times: ___/___/___, and here is my
   number squared: ___."``


.. admonition:: Tip

   `Code it at repl.it <https://replit.com/@launchcode/StringsExercisesPart3-1>`__.

**Section 2:  Debugging Practice**

The following code sample works, but it can be improved.

a. Assuming that ``advice`` remains a string, when will the code produce the
   wrong output?
b. Why will the code do this?
c. What should the programmer do to fix the code?

.. sourcecode:: python
   :linenos:

   advice = "Don't Panic"

   output = "The text, '{0}' contains {1} characters."

   print(output.format("Don't Panic", 11))

**Console Output**

::

   The text, 'Don't Panic' contains 11 characters.
