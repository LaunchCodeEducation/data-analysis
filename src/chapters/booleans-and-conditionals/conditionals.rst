Conditionals
============

.. index:: ! conditional

At the beginning of this chapter, we presented an example of an app that tracks
overdue library books.

.. admonition:: Example

   Consider an application that reminds you when you have an overdue book. The
   app sends you a message *only if* the due date has passed and you have not
   returned the book.

The app sends a message to the user if the condition "the book is overdue" is
true.

In Python and other programming languages, **conditional statements** are used
to either run or skip certain parts of the code. If a condition is ``True``,
then the program runs a specific block of code. Otherwise, the program ignores
that code and performs a different action.

.. _if:

``if`` Statements
-----------------

.. index:: ! if, code block

The most basic form of a conditional is an **if statement**. Here's how to
create one in Python:

.. sourcecode:: python
   :linenos:

   if condition:
      # Code statement 1
      # Code statement 2
      # Code statement 3
      # etc.

**Syntax Notes:**

#. The ``if`` statement consists of a header line and a body. The header line
   begins with the keyword ``if`` followed by a condition and then a
   colon (``:``).
#. ``condition`` is a boolean expression, which returns either ``True`` or
   ``False``. Examples include ``name == 'Jack'`` or ``points > 10``.
#. The statements underneath the header make up a **code block** (lines
   2 - 5). Note that these statements MUST be indented, and the code block
   can be any size.
#. The indented code runs if the condition evaluates to ``True``. If the
   condition is ``False``, this code gets ignored.
#. *The first unindented line marks the end of the if statement*.

Here is an example that checks the length of a string:

.. sourcecode:: python
   :linenos:

   text = "Don't Panic"

   if len(text) >= 10:
      print(text, "has more than 10 characters.")

``len(text)`` returns the number of characters in the string stored in
``text``. If the comparison is ``True``, then line 4 prints the message to the
console. If the string is less than 10 characters long, then no message
appears.

.. admonition:: Note

   Should you indent with tabs or spaces? This question usually starts BIG
   arguments within the programming world (think Marvel vs. DC or Hermione
   Granger marrying Harry instead of Ron).

   Many code editors automatically indent the lines within an ``if`` block, so most
   of the time you won't need to worry about how far to move in the cursor.
   However, here are the accepted guidelines for Python:

   #. Use SPACES, not tabs
   #. Four spaces are preferred
   #. Indentation must be consistent within a code block.

Try It!
^^^^^^^

In the editor below, try the following:

#. Run the code as-is.
#. Assign ``num`` a positive value, then re-run the code.
#. Indent line 6 to match line 4, then re-run the code. How did the output
   change?
#. Change the condition to print a message when ``num`` is positive.
#. **Advanced:** Use the :ref:`modulus operator <modulo>` (``%``) in line 3 in
   order to print a message when ``num`` is even.

.. raw:: html

   <iframe src="https://trinket.io/embed/python3/13c5ed88ed" width="100%" height="200" frameborder="0" marginwidth="0" marginheight="0"></iframe>

``else`` Clause
---------------

The example above either prints a message or nothing at all, depending on the
value of ``num``. What if we ALWAYS want to print something, but we want the
message to change based on the value of ``num``?

.. index:: ! else, ! if-else, branching

Adding an **else clause** to an ``if`` statement allows us to include code that
runs when the condition is ``False``.

.. admonition:: Example

   #. Run the following code as-is and examine the output.
   #. Change line 2 to ``book_status = 'overdue'`` and run the code again.
   #. How does the output change?

   .. raw:: html

      <iframe height="400px" width="100%" src="https://repl.it/@launchcode/Else-clause?lite=true" scrolling="no" frameborder="yes" allowtransparency="true"></iframe>

This structure is known as an **if/else statement**, and it allows our program
to **branch**. The flow of the program takes one of two paths when it reaches a
conditional, depending on whether the condition is ``True`` or ``False``.

.. _conditional-control-flow:

.. figure:: figures/conditional-flow.png
   :height: 350px
   :alt: A diagram showing how the flow of a program branches based on the value of the condition in an if-else statement. If the condition is true, one code block executes. If the condition is false, a different code block executes.

Check Your Understanding
------------------------

Use the code below to answer the following questions:

.. sourcecode:: python
   :linenos:

   name = input('Please enter a username: ')

   if len(name) >= 8:
      print("Welcome, " + name + "!")
   else:
      print("Invalid username.")

.. admonition:: Question

   What message gets printed if the user enters ``"Aahliyah"`` as their username?

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> Invalid username.</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> Welcome, name!</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, true)"> Welcome, Aahliyah!</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> Nothing is printed.</li>
      </ol>
      <p id="Q1"></p>

.. Answer = a

.. admonition:: Question

      Assume that you replace line 3 with ``if len(name) < 5:``. When would
      ``Invalid username`` get printed?

      .. raw:: html

         <ol type="a">
            <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> For any name with 4 characters or less</li>
            <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> For any name with 5 characters or less</li>
            <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> For any name with 4 characters or more</li>
            <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, true)"> For any name with 5 characters or more</li>
         </ol>
         <p id="Q2"></p>

.. Answer = d

.. admonition:: Question

   If you want to print the welcome message for any username SHORTER than 20
   characters, how should you change line 3?

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, false)"> <code class="pre">if len(name) > 20:</code></li>
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, false)"> <code class="pre">if len(name) >= 20:</code></li>
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, true)"> <code class="pre">if len(name) < 20:</code></li>
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, false)"> <code class="pre">if len(name) <= 20:</code></li>
      </ol>
      <p id="Q3"></p>

.. Answer: c
