Exercises: Errors and Debugging
===============================

Programmers spend a lot of time reviewing other people's code to help them find
and fix bugs.

Assume you are part of a team, and you must get the following code samples
working. Do NOT just clear the editor and start from scratch! Part of working
well with others is to recognize their effort and what they did correctly.
Throwing away all of their code just because you would do it differently is NOT
a helpful strategy.

.. admonition:: Note

   If your teacher added you to a :ref:`Trinket course <trinket-course-assignments>`, complete the exercises
   there.

   Otherwise, use the links below to code in your own free account.

Find and Fix Syntax Errors
--------------------------

The following code sample contains 3 syntax errors.

#. Before making any changes, run the code as-is to generate the first error
   message.
#. Use the error message to fix the first bug. Do NOT change anything in the
   code unless it involves fixing the first bug.
#. After changing the code, run the program again. If there is another bug in
   the program, you will see a different error message.
#. Repeat steps 2 and 3 until you fix all of the bugs and the program runs
   successfully.

.. admonition:: Example

   This program asks the user to enter an index value, and then it gives the
   letter from an alphabet string that has that index.

   .. raw:: html

      <iframe height="750px" width="100%" src="https://repl.it/@launchcode/LCHS-Debugging-Exercise-1?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

Find and Fix Runtime Errors
---------------------------

The following code sample contains 3 runtime errors.

#. Before making any changes, run the code as-is to generate the first error
   message.
#. Follow the same process you used above to fix the runtime errors. Note that
   syntax highlighting does NOT show all possible runtime errors.

.. admonition:: Example

   .. raw:: html

      <iframe height="750px" width="100%" src="https://repl.it/@launchcode/LCHS-Debugging-Exercise-2?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

Solve Logic Errors
------------------

#. The following code contains two logic errors.  When given a student's score
   on an exam, the program *should* convert the points earned into a
   percentage (points earned / points possible * 100). Find and fix the errors
   so that the program gives the correct result.

   .. admonition:: Example

      *Tip*: Use the following data to test the program and your fix.

      a. ``points_earned = 8``, ``points_possible = 10``, Correct answer =
         ``80.0%``
      b. ``points_earned = 11``, ``points_possible = 15``, Correct answer ≈
         ``73.33333333333333%``
      c. ``points_earned = 23.4``, ``points_possible = 25``, Correct answer =
         ``93.6%``

      .. raw:: html
      
         <iframe height="500px" width="100%" src="https://repl.it/@launchcode/LCHS-Debugging-Exercise-3?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

#. The next program should convert a student's percentage into a letter grade.
   The code follows a simple 10-point scale and allows for decimal results:

   A: 100% - 90%, B: 89 - 80, C: 79 - 70, D: 69 - 60, F: Any score under 60%.

   .. admonition:: Example

      Be sure to test all the *edge cases*. For example, 80% is a ``B``, but
      79.99...% is a ``C``.

      .. raw:: html

         <iframe height="700px" width="100%" src="https://repl.it/@launchcode/LCHS-Debugging-Exercise-4?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

#. The last code sample checks if a username is valid, but it's not working yet.
   Add ``print`` statements as directed to find and fix the logic errors.

   Username rules:

   a. Must be 5 - 10 characters long.
   b. Must only contain letters and numbers.
   c. Must contain at least 1 digit.

   Test names:

   a. ``"Me2"`` should be invalid (too short).
   b. ``"CoderGirl"`` should be invalid (no number).
   c. ``"rut*baga8"`` should be invalid (illegal symbol).
   d. ``"This1IsTooLong"`` should be invalid (too long).

.. admonition:: Example

   #. On line 10, add ``print(is_valid)`` to check if the conditional on line
      8 correctly assigns ``True`` and ``False`` based on the length of the
      username. Be sure to run the program with all four test names. ``Me2``
      and ``This1IsTooLong`` should return ``False``, while ``CoderGirl`` and
      ``rut*baga8`` should return ``True``.

      Is the conditional on line 8 doing its job correctly?
   #. If ``is_valid`` is ``False``, then the program should reject the
      username. The ``print`` statement on line 10 also lets you compare the
      value of ``is_valid`` to the final result. For example:

      ::

         False
         'Me2' is a valid username.

      In this case, ``is_valid`` is ``False`` at line 10, but the username
      still gets labeled as valid. This tells you that a logic error follows
      line 10.
   #. On line 18, add ``print(char, is_valid, has_digit)``. Make sure to indent
      the statement the same amount as the ``else`` on line 16.

      .. sourcecode:: python
         :lineno-start: 16

            else:
               is_valid = True
            print(char, is_valid, has_digit)

   #. Run the program again with all 4 test names. Note how the values of
      ``is_valid`` and ``has_digit`` change each time the loop repeats. Use the
      output to find and fix the logic error in the loop.
   #. *Hints*:

      a. The loop assigns ``is_valid`` to be ``True`` or ``False`` after every
         character in the username. Modify the code to preserve any ``False``
         result.
      b. There are at least two quick ways to accomplish this.

   .. raw:: html
   
      <iframe height="700px" width="100%" src="https://repl.it/@launchcode/LCHS-Debugging-Exercise-5?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

   *Bonus fix*: The loop runs after the length check passes *or* fails. How can
   we make it so that the loop runs only *if* the length test passes?
