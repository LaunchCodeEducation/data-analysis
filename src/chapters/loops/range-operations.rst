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

If we replaced line 1 in the code above with ``for num in range(1, 5)``, then
the loop variable ``num`` would take values of 1, 2, 3, and 4.

.. admonition:: Try It

   What should be the start and end values in ``range`` to print the following?

   ::

      HelloHello
      HelloHelloHello
      HelloHelloHelloHello
   
   .. raw:: html

      <iframe height="450px" width="100%" src="https://repl.it/@launchcode/LCHS-Range-Start-and-Stop?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true"></iframe>

Cool, ``range(start, stop)`` allows us to count upwards from any number we
want.

What if we want to count DOWN from one value to another? Also, what if we want
to change the loop variable by more than a single unit each iteration?

Set a Step Value
----------------

Suppose we want our loop variable to only be a set of even numbers (e.g. 0, 2,
4, 6...). We want to begin counting at 0 and then increase the loop variable
by 2 units instead of 1.

To make this happen, we need to add one more value inside ``range``. This is
called the *step value*, ``range(start_value, end_value, step_value)``.

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

In the editor below, change the values inside of ``range`` to accomplish the
following:

#. Print the numbers 0 - 5.
#. Print the numbers 33 - 45, including 45.
#. Print only the *odd* numbers from 0 - 20.
#. Print the numbers 25, 35, 45...95.
#. Print the numbers from -3 to -10.
#. Print by 3's from 15 to -21.

.. raw:: html

   <iframe height="450px" width="100%" src="https://repl.it/@launchcode/LCHS-Range-Step?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true"></iframe>

Use Variables in ``range``
--------------------------

To make a ``for`` loop run, we must tell Python exactly how many times we want
the loop body to repeat. However, sometimes this number changes each time the
program runs. Variables to the rescue!

.. admonition:: Tip

   Whenever possible, use *variables* instead of specific numbers inside
   ``range()``.

Paste these statements into the editor above (before the loop), and use the
variable names in ``range``:

.. sourcecode:: Python
   :linenos:

   start_value = int(input("Enter the FIRST number to print: "))
   end_value = int(input("Enter the LAST number to print: "))
   step_value = int(input("Enter the step value for the loop: "))

Repeat each of the items in the :ref:`Try It <range-tryit>` section above. Enter the start, stop, and step values to print the
desired output.

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

For the program above, replace the ``for`` statement with this:

.. sourcecode:: Python

   for num in range(start_value, end_value+1, step_value):

For tasks 1 - 4, the expression ``end_value + 1`` makes sure that the value we
type will be included in the loop. With the negative stop values in tasks 5 and
6, we need to use ``end_value - 1``.

.. admonition:: Try It

   Run the following program. Enter different words to see how the behavior
   changes.

   .. raw:: html

      <iframe height="400px" width="100%" src="https://repl.it/@launchcode/LCHS-Range-Expressions?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true"></iframe>
   
   When Python executes the ``for`` statement, the expression ``len(word)``
   returns the length of the string. So if ``word = "Hi"``, then
   ``range(len(word))`` acts just like ``range(2)``.

Check Your Understanding
------------------------

.. raw:: html

   <script type="text/JavaScript">
      function evaluateMC(id, correct) {
         if (correct) {
            document.getElementById(id).innerHTML = 'Yep!';
            document.getElementById(id).style.color = 'blue';
         } else {
            document.getElementById(id).innerHTML = 'Nope!';
            document.getElementById(id).style.color = 'red';
         }
      }
   </script>

.. admonition:: Question

   In the command ``range(3, 10, 2)``, the second argument (``10``) specifies that
   ``range`` should:

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, true)"> generate a set of values that stops at 9 (including 9).</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> generate a set of values that starts at 10 (including 10).</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> generate a set of values starting at 3 that stops at 10 (including 10).</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> generate a set of values using every 10th number between 3 and 10.</li>
      </ol>
      <p id="Q1"></p>

.. Answer = a.

.. admonition:: Question

   What command correctly generates the values ``2, 5, 8`` in that order?

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> <strong style="color:#419f6a">range(2, 5, 8)</strong></li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> <strong style="color:#419f6a">range(2, 8, 3)</strong></li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, true)"> <strong style="color:#419f6a">range(2, 10, 3)</strong></li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> <strong style="color:#419f6a">range(8, 1, -3)</strong></li>
      </ol>
      <p id="Q2"></p>

.. Answer = c

.. admonition:: Question

   What happens if you give range only one argument, like ``range(14)``?

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, false)"> It will generate a set of values starting at 1 and ending with the number in the ().</li>
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, false)"> It will generate a set of values starting at 1 up to but NOT including the number in the ().</li>
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, false)"> It will generate a set of values starting at 0 and ending with the number in the ().</li>
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, true)"> It will generate a set of values starting at 0 up to but NOT including the number in the ().</li>
      </ol>
      <p id="Q3"></p>

.. Answer = d
