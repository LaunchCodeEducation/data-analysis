More on ``range``
=================

In one example from the last section, we used ``range`` to make the loop run
four times:

.. sourcecode:: Python
   :linenos:

   for num in range(4):
      print(num)
      print("Hello" * num)

For each iteration, the variable ``num`` took on a new value (0, 1, 2, or 3).

What if we wanted the loop to use the sequence 1, 2, 3, 4 instead?

Set Start and End Values
------------------------

Whenever we use ``range(value)`` in a ``for`` statement, Python always begins
counting with 0. To start counting at a different number, we need to include
that value inside the ``()`` in addition to a stop value.

Instead of ``range(value)``, a more detailed version of the keyword is
``range(start_value, end_value)``. The starting value is included in the
counting for the loop, but the end value is NOT.

.. admonition:: Syntax Example

   .. sourcecode:: py

      for num in range (start_value, end_value):
         # do something...

If we replaced line 1 in the code above with ``for num in range(1, 5)``, then
the loop variable ``num`` would take values of 1, 2, 3, and 4.

.. admonition:: Try It

   Run the following code to see how using different start and stop values effects the output.

   .. replit:: py
      :slug: StartAndStop
      :linenos:

      # Change the start and stop values in 'range'. How does this affect the output?

      for num in range(1, 4):
         print("Hello" * num)
   

Now, what if we want to count DOWN from one value to another or change the loop variable by more than a single unit each iteration?

.. index:: ! step value range 

Set a Step Value
----------------

Suppose we want our loop variable to only be a set of even numbers (e.g. 0, 2,
4, 6...). We want to begin counting at 0 and then increase the loop variable
by 2 units instead of 1.

To make this happen, we need to add one more value inside ``range``. This is
called the **step value**, ``range(start_value, end_value, step_value)``.

.. admonition:: Syntax Example

   .. sourcecode:: py

      for num in range(start_value, end_value, step_value):
         # do something ...

.. admonition:: Examples

   To count from 0 to 20 by 2's, use:

   .. sourcecode:: Python

      for num in range(0, 21, 2)

   To count up by 5's, use:

   .. sourcecode:: Python

      for num in range(0, 21, 5)

   We can even count DOWN from a higher number to a lower one. The step value
   just needs to be negative:

   .. sourcecode:: Python

      for num in range(50, 39, -1)   # Counts from 50 down to 40

.. admonition:: Note

   For ``range()``, the start and step values are OPTIONAL.

.. _range-tryit:

Try It!
-------

Change the values inside of ``range`` to accomplish the
following:

#. Print the numbers 0 - 5.
#. Print the numbers 33 - 45, including 45.
#. Print only the *odd* numbers from 0 - 20.
#. Print the numbers 25, 35, 45...95.
#. Print the numbers from -3 to -10.
#. Print by 3's from 15 to -21.

.. replit:: py
   :slug: RangeOptions
   :linenos:

   # Change the start, stop, and step values in range to solve tasks 1 - 6 in the text.
   # Tip: Use the 'clear' button in the console to remove old outputs.

   for num in range(8):
      print(num)

Use Variables in ``range``
--------------------------

To make a ``for`` loop run, we must tell Python exactly how many times we want
the loop body to repeat. However, sometimes this number changes each time the
program runs. Variables to the rescue!  
Whenever possible, use *variables* instead of specific numbers inside ``range()``.

.. admonition:: Try It

   Let's try printing a ``for`` loop using the following variables to set the range.

   .. replit:: py
      :slug: RangeAndVariables

      start_value = int(input("Enter the FIRST number to print: "))
      end_value = int(input("Enter the LAST number to print: "))
      step_value = int(input("Enter the step value for the loop: "))



.. admonition:: Warning

   A common mistake for new coders is to forget that the end value in
   ``range`` is NOT assigned to the loop variable at any time.

After you pasted in the ``input`` statements and ran the program, did you have
to type ``0, 6, 1`` to get the numbers 0 - 5 to show in the console? The
``input`` statement implies that we want our typed end value to show up, but
using the variable in ``range`` skips that number.

How do we fix this?

Use Expressions in ``range``
----------------------------

Not only can we use variables inside ``range``, we can also use *expressions*,
which we practiced in the :ref:`Data and Variables <expressions>` chapter.

.. admonition:: Try It!

   .. replit:: py
      :slug: RangeAndExpressions01

      for num in range(start_value, end_value+1, step_value):

The ``end_value`` above, will add ``1`` to the inital ``end_value``. 
By adding to your ``end_value``, will increase loops that have a positive, or increasing, ``step_value``.

With the negative ``end_values``, or decreasing ``step_values``, adding to your ``end_value``
may actually shorten the length of your final loop.  

In order to extend a negative range, try reducing your ``end_value``.
By reducing, or subtracting, from your ``end_value`` you will extend loops involving negative 
numbers or negative ``step_values``.  In turn, this will shorten
loops between positive numbers, or with positive ``step_values``.

.. admonition:: Try It!

   .. replit:: py
      :slug: RangeAndExpressions02

      for num in range(start_value, end_value-1, step_value):

Expressions are not limited to standard arithmetic operators.

.. admonition:: Try It

   Run the following program. Enter different words to see how the behavior
   changes.

   .. replit:: py
      :slug: RangeExpressions
      :linenos:

      word = "Python"

      for num in range(len(word)):
         print(word*num)

   When Python executes the ``for`` statement, the expression ``len(word)``
   returns the length of the string. So if ``word = "Hi"``, then
   ``range(len(word))`` acts just like ``range(2)``.

Check Your Understanding
------------------------

.. admonition:: Question

   In the command ``range(3, 10, 2)``, the second argument (``10``) specifies that
   ``range`` should:

   a. generate a set of values that stops at 9 (including 9).
   b. generate a set of values that starts at 10 (including 10).
   c. generate a set of values starting at 3 that stops at 10 (including 10).
   d. generate a set of values using every 10th number between 3 and 10.
   
.. Answer = a.

.. admonition:: Question

   What command correctly generates the values ``2, 5, 8`` in that order?

   a. ``range(2, 5, 8)``
   b. ``range(2, 8, 3)``
   c. ``range(2, 10, 3)``
   d. ``range(8, 1, -3)``

.. Answer = c

.. admonition:: Question

   What happens if you give range only one argument, like ``range(14)``?

   a. It will generate a set of values starting at 1 and ending with the number in the ().
   b. It will generate a set of values starting at 1 up to but NOT including the number in the ().
   c. It will generate a set of values starting at 0 and ending with the number in the ().
   d. It will generate a set of values starting at 0 up to but NOT including the number in the ().

.. Answer = d
