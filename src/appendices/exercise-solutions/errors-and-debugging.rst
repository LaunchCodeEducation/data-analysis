

Exercises: Errors and Debugging Solutions
=========================================

Find and Fix Syntax Errors
--------------------------

.. _errors-and-debugging-exercise-solutions-part1:

#. **Error 1: Line 6**  Correct syntax should look like this:

   ::

      value = int(input("Enter an index value: "))
#. **Error 2: Line 9** Correct syntax should look like this

   ::

      if value > len(alphabet):
#. **Error 3: Line 12** Correct syntax should look like this:

   ::

       print("The letter at index {0} is '{1}'.".format(index, alphabet[index]))


:ref:`Back to Exercises<errors-and-debugging-exercises>`


Find and Fix Runtime Errors
---------------------------

This `code sample <https://replit.com/@launchcode/DebuggingExercises02>`__ contains 3 runtime errors.

#. Before making any changes, run the code as-is to generate the first error
   message.
#. Follow the same process you used above to fix the runtime errors. Note that
   syntax highlighting does NOT show all possible runtime errors.

Solve Logic Errors
------------------

#. This `code <https://replit.com/@launchcode/DebuggingExercises03>`__ contains two logic errors.  When given a student's score
   on an exam, the program *should* convert the points earned into a
   percentage (points earned / points possible * 100). Find and fix the errors
   so that the program gives the correct result.

   *Tip*: Use the following data to test the program and your fix.

   a. ``points_earned = 8``, ``points_possible = 10``, Correct answer =
      ``80.0%``
   b. ``points_earned = 11``, ``points_possible = 15``, Correct answer ≈
      ``73.33333333333333%``
   c. ``points_earned = 23.4``, ``points_possible = 25``, Correct answer =
      ``93.6%``

#. This `program <https://replit.com/@launchcode/DebuggingExercises04>`__ should convert a student's percentage into a letter grade.
   The code follows a simple 10-point scale and allows for decimal results:

   A: 100% - 90%, B: 89 - 80, C: 79 - 70, D: 69 - 60, F: Any score under 60%.

   Be sure to test all the *edge cases*. For example, 80% is a ``B``, but
   79.99...% is a ``C``.

#. The last `code sample <https://replit.com/@launchcode/DebuggingExercises05>`__ checks if a username is valid, but it's not working yet.
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

   *Bonus fix*: The loop runs after the length check passes *or* fails. How can
   we make it so that the loop runs only *if* the length test passes?
