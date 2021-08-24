Studio: Functions
==================

The ``reverse`` method flips the order of the elements within an list.
However, ``reverse`` does not affect the digits or characters within those
elements.

.. admonition:: Example

   .. sourcecode:: py
      :linenos:

      fun_list = ['hello', 'world', 123, 'orange']

      fun_list.reverse()
      print(fun_list)

   **Console Output**

   ::

      ['orange', 123, 'world', 'hello']

What if we wanted the reversed list to be
``['egnaro', 321, 'dlrow', 'olleh']``?

Let's have some fun by creating a process that reverses BOTH the order of the
entries in an list AND the order of characters within the individual elements.

Remember that a function should perform only one task. To follow this best
practice, we will solve the list reversal by defining two functions - one that
reverses the characters in a string (or the digits in a number) and one that
flips the order of entries in the list.

Fork and clone the starter code from the `remote repository <https://github.com/LaunchCodeEducation/functions-studio-data-analysis>`__ 

.. admonition:: Note

   If this process is not working for you, that is okay! While we want you to get the hang of forking and cloning remote repos, we also want you to focus on coding!
   Please use the following repls if you need to.

   #. `Parts 1-3 <https://repl.it/@launchcode/FunctionsStudio01-03>`__
   #. `Bonus Mission 1 <https://replit.com/@launchcode/FunctionsStudio-Bonus01>`__
   #. `Bonus Mission 2 <https://replit.com/@launchcode/FunctionsStudio-Bonus02>`__

Reverse Characters
-------------------

.. TODO: Check this reference.

1. In the *composing functions* section, we examined a function that
   reverses the characters in a string using the
   ``split`` and ``join`` methods. Let's rebuild that function now.

   a. Define the function as ``reverse_characters``. Give it one parameter, which will
      be the string to reverse.
   b. Within the function, ``split`` the string into an list, then reverse the
      list.
   c. Use ``join`` to create the reversed string and *return* that string from the
      function.
   d. Below the function, define and initialize a variable to hold a string.
   e. Use ``print(reverse_characters(my_variable_name))`` to call the function and verify
      that it correctly reverses the characters in the string.
   f. *Optional*: Use method chaining to reduce the lines of code within the
      function.

Work on parts 1-3 in ``functionsstudio01-03.py``.

.. admonition:: Tip

   Use these sample strings for testing:

   a. ``'apple'``
   b. ``'LC101'``
   c. ``'Capitalized Letters'``
   d. ``'I love the smell of code in the morning.'``

Reverse Digits
---------------

2. The ``reverse_characters`` function works great on strings, but what if the
   argument passed to the function is a number? Using
   ``print(reverse_characters(1234))`` results in an error, since
   ``split`` only works on strings (TRY IT). When passed a number, we want the
   function to return a number with all the digits reversed (e.g. 1234 converts
   to 4321 and NOT the string ``"4321"``).

   a. Add an ``if`` statement to ``reverse_characters`` to check the ``type`` the
      parameter.
   b. If ``type`` is 'string', return the reversed string as before.
   c. If ``type`` is 'integer', convert the parameter to a string, reverse the
      characters, then convert it back into a number.
   d. Return the reversed number.
   e. Be sure to print the result returned by the function to verify that your code
      works for *both strings and numbers*. Do this before moving on to the
      next exercise.

.. admonition:: Tip

   Use these samples for testing:

   a. ``1234``
   b. ``'LC101'``
   c. ``8675309``
   d. ``'radar'``

Complete Reversal
------------------

3. Now we are ready to finish our complete reversal process. Create a new
   function with one parameter, which is the list we want to change. The
   function should:

   a. Define and initialize an empty list.
   b. Loop through the old list.
   c. For each element in the old list, call ``reverse_characters`` to flip the
      characters or digits.
   d. Add the reversed string (or number) to the list defined in part 'a'.
   e. Return the final, reversed list.
   f. *Be sure to print the results from each test case in order to verify your
      code*.

.. admonition:: Tip

   Use this sample data for testing.

   .. list-table::
      :header-rows: 1

      * - Input
        - Output
      * - ``['apple', 'potato', 'Capitalized Words']``
        - ``['sdroW dezilatipaC', 'otatop', 'elppa']``
      * - ``[123, 8897, 42, 1138, 8675309]``
        - ``[9035768, 8311, 24, 7988, 321]``
      * - ``['hello', 'world', 123, 'orange']``
        - ``['egnaro', 321, 'dlrow', 'olleh']``

Bonus Missions
---------------

4. Define a function with one parameter, which will be a string. The function
   must do the following:

   a. Have a clear, descriptive name like ``fun_phrase``.
   b. Retrieve only the last character from strings with lengths of 3 or less.
   c. Retrieve only the first 3 characters from strings with lengths larger
      than 3.
   d. Use a template literal to return the phrase ``We put the '___' in '___'.``
      Fill the first blank with the modified string, and fill the second blank
      with the original string.
   e. Work on this function in ``functionsstudio-bonus01.py``.

#. Now test your function:

   f. Outside of the function, define the variable ``str`` and initialize it
      with a string (e.g. ``'Functions rock!'``).
   g. Call your function and print the returned phrase.

#. The area of a rectangle is equal to its *length x width*.

   a. Define a function with the required parameters to calculate the area of a
      rectangle.
   b. The function should *return* the area, NOT print it.
   c. Call your area function by passing in two arguments - the length and
      width.
   d. If only one argument is passed to the function, then the shape is a
      square. Modify your code to deal with this case.
   e. Use a template literal to print, "The area is ____ cm^2."
   f. Work on this function in ``functionsstudio-bonus02.py``.

.. admonition:: Tip

   Use these test cases.

   a. length = 2, width = 4 (area = 8)
   b. length = 14, width = 7 (area = 98)
   c. length = 20 (area = 400)
