.. _strings-exercise-solutions:

Exercise Solutions: Strings
======================================

Remember, the solutions below represent *ONE* way to solve the exercise.
If your output matches what is being asked for, you have correctly solved the exercise.

Part One: Bracket Notation
--------------------------

.. _strings-exercise-solutions1.2:

Bracket Notation Basics
^^^^^^^^^^^^^^^^^^^^^^^

Use bracket notation to:

1. Print a slice of the first 12 characters from
   ``"Strings_are_sequences_of_characters."``

   .. sourcecode:: python

      print(text[:12])


2. Print a slice of the last 12 characters from the same string. You should
   NOT have to count the index values yourself!

   .. sourcecode:: python

      print(text[-12:])

3. Print a slice of the middle 12 characters from the same string.

   .. sourcecode:: python
   
      print(text[12:24])


:ref:`Return to the exercises<strings-exercises>`

.. _strings-exercise-solutions1.3:

Looping Through a String
^^^^^^^^^^^^^^^^^^^^^^^^

Use index values to loop *backwards* through a string:

1. First, print one letter per line.

   .. sourcecode:: python

      max_index = len(word)-1
      for index in range(max_index, -1, -1):
         print(word[index])

2. Next, instead of one letter per line, use the accumulator pattern to build
   up and print the reversed string. For example, if given the string
   ``'good'``, your program prints ``doog``.

   .. sourcecode:: python

      new_word = ""
      for index in range(max_index, -1, -1):
         new_word += word[index]

      print(new_word)

3. Finally, use concatenation to print the combination of the original and
   reversed string. For example, given the string ``'tomato'``, your program
   prints ``tomatootamot``. (If you want to be fancy, include the ``|``
   character to make the output look almost like a mirrored image: ``tomato | otamot``). 

:ref:`Return to the exercises<strings-exercises>`

Part Two: String Methods and Operations
---------------------------------------

.. _strings-exercise-solutions2.1:

String Methods and Data Types
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The ``len()`` function returns the number of characters in a string. However,
the function will NOT give us the length of an integer. If ``num = 1001``,
then ``len(num)`` throws an error instead of returning ``4``.

1. Use ``str()`` to change ``num`` from an ``int`` to a string data type.
2. Print the length (number of digits) in ``num``.

   .. sourcecode:: python

      print(len(str(num)))

3. Modify your code to print the number of digits in a ``float`` value (e.g.
   ``num = 123.45`` has 5 digits but a length of 6). The digit count should
   NOT include the decimal point.

   .. sourcecode:: python

      num = 123.45
      new_num = str(num).replace(".", "")
      print(len(new_num))

4. What if ``num`` could be EITHER an integer or a decimal? Add an ``if/else``
   statement so your code can handle both cases.  (Hint: Consider using the
   ``find()`` method or the ``in`` operator to check if ``num`` contains a
   decimal point).

   .. sourcecode:: python

      if '.' in str(num):
         print(len(str(num)) - 1)
      else:
         print(len(str(num)))

:ref:`Return to the exercises<strings-exercises>`

.. _strings-exercise-solutions2.2:

Loops, Conditionals, and Strings! Oh my!
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Given ``word = 'bag'``:

1. Set up a loop to iterate through the string of lowercase vowels,
   ``'aeiou'``.
2. Inside the loop, create a new string from ``word``, but with a different
   vowel. Use the ``replace()`` string method.
3. Print the new string.
    
   .. sourcecode:: python

      word = "bag"
      vowels = "aeiou"
   
      for vowel in vowels:
         new_word = word.replace("a", vowel)
         print(new_word)

:ref:`Return to the exercises<strings-exercises>`

.. _strings-exercise-solutions2.3:

Method Chaining Fun with DNA
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Use the ``strip()`` method to remove the leading and trailing whitespace,
   and then print the result.
2. Change all of the letters in the DNA string to UPPERCASE and print the
   result.

   .. sourcecode:: python

      dna = dna.strip().upper()
      print(dna)

3. Let's use string methods to do more work on the same DNA strand:

   a. Use ``replace()`` to remove the sequence ``'GCT'``, and then print the altered
      strand. Don't forget about the extra hyphen!

      .. sourcecode:: python

         dna = dna.replace("-GCT","")
         print(dna)

   b. Look for the sequence ``'CAT'`` with ``find()``. If found print, ``'CAT
      found'``, otherwise print, ``'CAT NOT found'``.

      .. sourcecode:: python

         if dna.find("CAT") > -1:
            print("CAT gene found")
         else:
            print("Cat gene NOT found")

   c. Use ``count()`` to find the number of hyphens (``-``) in the string, then
      print the number of *genes* (in this case, a gene is a set of 3 letters) in the DNA strand. Note
      that the number of genes will be 1 more than the number of hyphens. 

      .. sourcecode:: python

         hyphen_count = dna.count("-")
         gene_count = hyphen_count+1

         print(hyphen_count, gene_count)

   d. Finally, use an f-string to print the output
      ``"The DNA string is ___ characters long and contains ___ genes."`` Fill in
      the blanks with the length of the string and the number of genes.

      .. sourcecode:: python

         print("The DNA string is {0} characters long and contains {1} genes.".format(len(dna), gene_count))

:ref:`Return to the exercises<strings-exercises>`

Part Three: String Formatting
-----------------------------

Template Literals
^^^^^^^^^^^^^^^^^

.. _strings-exercise-solutions3.1:

Assign your favorite, school-appropriate number and word to two variables.
   
1. Use ``format()`` and index values to print the string,
   ``"Here is my number: ___, and here is my word: ___, and here is my
   number again: ___."``

   .. sourcecode:: python

      output = "Here is my number: {0}, and here is my word: {1}, and here is my number again: {0}."

      print(output.format(my_num, my_word))

2. Print the string, ``"Here is my word 3 times: ___/___/___, and here is my
   number squared: ___."``


:ref:`Return to the exercises<strings-exercises>`


Debugging Practice
^^^^^^^^^^^^^^^^^^

.. _strings-exercise-solutions3.2:

*No starter code for this one.*

The following code sample works, but it can be improved.

1. Assuming that ``advice`` remains a string, when will the code produce the wrong output?
2. Why will the code do this?
3. What should the programmer do to fix the code?

.. sourcecode:: python

   #One option is to avoid hard coding the print line and use variables.
   
   advice = "Don't Panic"

   output = "The text, '{0}' contains {1} characters."
   
   print(output.format(advice, len(advice)))


:ref:`Return to the exercises<strings-exercises>`