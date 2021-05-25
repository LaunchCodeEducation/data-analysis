Nested Conditionals
===================

By using an ``if/else`` statement, we produce two branches for our code to
follow. We can add more branches to our program flow by combining conditionals.

Let's see how this works by solving the following problem:

.. admonition:: Example

   Write a program that:

   #. Prompts the user to enter a whole number.
   #. If the number is odd, print nothing.
   #. If the number is even, print "EVEN!" If the number is also positive,
      print "POSITIVE".

Our first attempt at a solution might look like this:

.. sourcecode:: python
   :linenos:

   entry = int(input('Enter a whole number: '))

   if entry%2 == 0:
      print("EVEN!")

   if entry > 0:
      print("POSITIVE")

**Console Output**

::

   Enter a whole number: 7

   POSITIVE

When we enter ``7`` in the prompt, we want the program to print nothing. However,
we see the output ``POSITIVE``. The code doesn't work as we want. Why not?

Written this way, the two conditionals are separate from each other. The result
from one has no influence on the other. Checking ``entry`` as even or odd works
fine on its own. However, the second check gets carried out whether or not
``entry%2 == 0`` is ``True`` or ``False``. :ref:`Remember <if>`, the ``if`` condition
does not apply after the first unindented line. 

.. index::
   single: conditional; nested

We want to check if ``entry`` is positive ONLY IF the number is even. To do
this, we need to put the second conditional *inside* the first. This code
structure is called a **nested conditional**. The result of the first
conditional determines whether or not to consider the second.

.. admonition:: Try It!

   Run this code several times and choose different values for ``entry`` (even,
   odd, positive, negative) to prove that it works as desired. Nice, huh?

   .. raw:: html

      <iframe height="400px" width="100%" src="https://repl.it/@launchcode/LCHS-Positive-and-Even?lite=true" scrolling="no" frameborder="no" allowtransparency="true"></iframe>

   Try removing the indentation for lines 6 & 7 to see how the output changes!

Notice that when we put one conditional inside another, the body of the nested
conditional is indented by two levels rather than one. In Python, the indentation 
of an ``if`` statement determines if it is nested. For an ``if``
statement to run inside another, it must be indented more than the outer conditional. 

Nesting Also Works With ``else``
--------------------------------

In the examples above, we left out the ``else`` clauses from the conditionals.
Let's take nesting a step further by including ``else`` clauses:

.. admonition:: Try It!

   **PREDICT**: What will this program print for the following words?

   #. ``the``
   #. ``kale``
   #. ``rutabaga``

   .. raw:: html

      <iframe height="500px" width="100%" src="https://repl.it/@launchcode/LCHS-Nested-Conditionals?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

   **DISCOVER**: Run the program to check your predictions.

.. admonition:: Tip

   In Python, the amount of indentation tells us exactly which ``else`` clause belongs to which ``if`` statement.

This diagram shows the *flow of control* for this program:

.. figure:: figures/nested-control-flow.png
   :height: 350px
   :alt: A diagram showing how the flow of a program branches based on the value of the condition in a nested if-else statement.


Check Your Understanding
------------------------

.. admonition:: Question

   What is printed when the following code runs?

   .. sourcecode:: python
      :linenos:

      num = 7

      if num % 2 == 0:
         if num % 2 == 1:
            print("odd")

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> The code won't run due to invalid syntax.</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> odd</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> even</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, true)"> The code runs but doesn't print anything.</li>
      </ol>
      <p id="Q1"></p>

.. Answer = d

.. admonition:: Question

   What is printed when the following code runs?

   .. sourcecode:: python
      :linenos:

      answer_1 = 'yes'
      answer_2 = 'no'
      

      if answer_1 == 'yes':
         if answer_2 == 'yes':
            print("Both of you agree!")
         else:
            print("You two need to work this out.")
      else:
         if answer_2 == 'yes':
            print("Stop arguing and work it out.")
         else:
            print("Clean your bathroom anyway!")

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> Both of you agree!</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, true)"> You two need to work this out.</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> Stop arguing and work it out.</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> Clean your bathroom anyway!</li>
      </ol>
      <p id="Q2"></p>

.. Answer = b
