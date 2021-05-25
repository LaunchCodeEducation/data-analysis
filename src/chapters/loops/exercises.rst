Exercises: Loops
================

   Loops simplify repetitive tasks!

.. figure:: figures/loop-comic.png
   :alt: Image showing how Bart Simpson could use Python to write his sentences on a chalkboard.

   Image from `Bart's Blackboard <http://bartsblackboard.com/category/season-2/page/2/>`__, Season 2, Episode 11 (Jan 24, 1991)

``for`` Practice
-----------------

.. admonition:: Note

   If your teacher added you to a :ref:`Trinket course <trinket-course-assignments>`, complete the exercises
   there.

   Otherwise, use the links below to code in your own free account.

#. Construct ``for`` loops that accomplish the following tasks:
   (`repl.it code <https://repl.it/@launchcode/LCHS-For-Loop-Exercises-1>`__ or `Trinket code <https://trinket.io/python/71cbf8d913?runOption=run&showInstructions=true>`__)

   a. Print the numbers 0 - 20, one number per line.
   b. Print only the ODD values from 3 - 29, one number per line.
   c. Print the EVEN numbers 12 down to -14 in descending order, one number
      per line.
   d. Print the numbers 50 down to 20 in descending order, but only
      if the numbers are multiples of 3.

#. Given the string ``'LaunchCode'``, code two ``for`` loops to do the
   following: (`repl.it <https://repl.it/@launchcode/LCHS-For-Loop-Exercises-2>`__
   or `Trinket <https://trinket.io/python/01eb624abf?showInstructions=true>`__)

   a. Print out each character of the string, one letter per line. Do this
      WITHOUT using index values.
   b. Now use index values to print each character of the string---in reverse
      order---to a new line. Recall that you can access a single character from
      a string with the syntax ``var_name[index]``, where ``index`` is an
      integer value, and ``var_name`` is the variable used to store the string.

#. Given the string ``gibberish =
   'Vna#hewzB*rQhT%yq^lv %iPwgOexWo &C^oUoGSdtJLj'``, print every fifth
   character, including the first character. Use index values and
   ``range(start, stop, step)``.

   *Hint*: Instead of figuring out the ``stop`` value by counting all of the
   characters in ``gibberish`` yourself, make Python do it for you! Recall that
   ``len(gibberish)`` returns the length of the string stored in the variable.

   `repl.it file <https://repl.it/@launchcode/LCHS-For-Loop-Exercises-3>`__ or
   `Trinket file <https://trinket.io/python/04ee784ec9?showInstructions=true>`__

Bonus
^^^^^

Repeat the previous problem, but:

a. Replace ``range(start, stop, step)`` with ``range(len(gibberish))``.
b. Use an ``if`` statement and the modulus (``%``) operator to check if the
   index is divisible by 5.
c. If ``True``, print the character. If ``False``, do not print the character.
d. The output should be the same as before.

``while`` Practice
-------------------

Define three variables for a spacecraft---one for the starting fuel level,
another for the number of astronauts aboard, and the third for the altitude the
spacecraft reaches. Assign each variable an initial value of 0.

While loop starter code: `repl.it <https://repl.it/@launchcode/LCHS-While-Loop-Exercises>`__
or `Trinket <https://trinket.io/python/21d6e91b92?showInstructions=true>`__.

4. Construct ``while`` loops to do the following:

   #. Ask the user for the starting fuel level. The loop should continue until
      the user enters a value between 5000 and 30000. If the user submits a
      number outside of the range, print ``"Invalid entry."``
   #. Use a second loop to prompt the user for the number of astronauts
      (up to a maximum of 7). Validate the entry by having the loop continue
      until the user enters an integer from 1 - 7. For numbers outside of the
      range, print ``"Invalid entry."``

#. Use a third ``while`` loop to update the fuel and the altitude of the
   spacecraft. Each iteration, decrease the fuel level by 100 units for each
   astronaut aboard. Also, increase the altitude by 50 kilometers.
   
   *Hint*: The loop should end when there is not enough fuel to boost the crew
   another 50 km, so the fuel level might not reach 0.

#. After the loops finish, print the result using the phrase, ``The spacecraft
   gained an altitude of ___ km and has ___ kg of fuel left.`` Fill in the
   blanks with the altitude and fuel level values.
#. If the altitude is 2000 km or higher, add ``"Orbit achieved!"`` to the
   output. Otherwise add, ``"Failed to reach orbit."``

**Sample Output**

::

   Enter starting fuel level (5000 - 30000):  22000
   Enter the number of astronauts (1 - 7):  3
   The spacecraft gained an altitude of 3650 km and has 100 kg of fuel left. Orbit achieved! 

The Accumulator Pattern
-----------------------

Accumulator starter code: `repl.it <https://repl.it/@launchcode/LCHS-Accumulator-Exercises>`__
or `Trinket <https://trinket.io/python/506a6d99b0?showInstructions=true>`__.

Use two ``input`` statements to prompt the user for a ``start_value`` and an
``end_value``. Both inputs should be integers.

8. Use a loop to add up all of the numbers from ``start_value`` to
   ``end_value``. Use the variable ``total`` as the accumulator. Print ``"The
   sum of the numbers from ___ to ___ is ___."`` Fill in the blanks with the
   values for ``start_value``, ``end_value``, and ``total``.

#. Define a variable to hold the string ``'It was a bright cold day in April,
   and the clocks were striking thirteen.'`` Use the accumulator pattern to
   build a new string. It should contain all of the characters in the original
   string, but without any vowels.  For this task, y does NOT count as a vowel.
   Print the new string.

Challenge
---------

If our spacecraft gets hijacked by space pirates, the astronauts can activate
a self-destruct sequence to provide some drama for the viewers at home.

In order to prevent a rogue astronaut from activating the code, it takes *two*
crew members to begin the countdown. Each person must enter a different code,
after which the computer will "zip" them together before overloading the
engines.

In a new code file, construct a loop that combines two strings together,
alternating the characters from each source. For now, be careful to make both
strings the same length.

.. admonition:: Examples

   #. If ``string = "1234"`` and ``other_string = "5678"``, then the output will
      be ``"15263748"``.
   #. If ``code_1 = "ABCDEF"`` and ``code_2 = "notyet"``, then the output will be
      ``"AnBoCtDyEeFt"``.
   #. If ``ka = "LoOt"`` and ``blam = "oku!"``, then the output will be
      ``"LookOut!"``.
