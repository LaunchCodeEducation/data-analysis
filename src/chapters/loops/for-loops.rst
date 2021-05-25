``for`` Loops
=============

If you were to instruct your pet turtle to draw a square in the sand, your
commands would quickly become quite tedious. You must tell your pet to move
then turn, move then turn, etc. four times. If you want your turtle to draw a
hexagon, an octagon, or a polygon with 42 sides, it would be a nightmare to
repeat all the commands!

.. admonition:: Example

   Turtle statements for drawing a square:

   .. sourcecode:: python
      :linenos:

      import turtle

      pet = turtle.Turtle()

      pet.forward(50)
      pet.left(90)
      pet.forward(50)
      pet.left(90)
      pet.forward(50)
      pet.left(90)
      pet.forward(50)
      pet.left(90)

   Note: If you have not practiced with turtles in class yet, check out the
   :ref:`Python Turtles <turtle-guide>` appendix.

Time to use iteration! The first Python iteration tool we will learn
is the ``for`` loop. 

``for`` Loop Syntax
-------------------

.. index::
   single: loop; for

.. index:: ! for loop

A **for loop** repeats a specific set of code statements a specific number of
times. When a ``for`` loop begins, we must declare exactly how many times it
will run.

Play around with the basic syntax of a ``for`` loop.

.. admonition:: Try It

   This program prints the integers 0 through 20, one number per line.

   .. raw:: html

      <iframe src="https://trinket.io/embed/python3/f5e2eaec5c?runOption=run" width="100%" height="400" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

   #. What do you notice about the numbers printed in the console vs. the
      value inside ``range()``?
   #. Try changing the value inside ``range()``. What values throw an error?
   #. What happens when you indent line 4 to match line 2?

Let's break down the syntax piece by piece, so we can begin to understand how
``for`` loops are structured.

.. index::
   single: for loop; variable

#. In line 1, ``num`` is called the **loop variable**. Each time the loop
   executes, ``num`` gets assigned a new value.
#. Line 2 begins the loop body. The loop body is ALWAYS indented. The
   indentation determines exactly what statements are “in the loop”. You saw
   this when you indented line 4 to match line 2. Originally, line 4 was
   outside of the loop and ran only once. By indenting line 4, it becomes part
   of the loop body and gets repeated multiple times.
#. The *first* unindented line after the ``for`` statement marks the end of the
   loop body.
#. The loop body can contain any number of statements.
#. The number of times the loop body runs depends on the value in ``range()``.

Line By Line
^^^^^^^^^^^^

Let's modify the code just a little to follow the operation of a ``for`` loop.

.. admonition:: Example

   .. sourcecode:: Python
      :linenos:

      for num in range(4):
         print(num)
         print("Hello" * num)

      print("Done!")

   **Console Output**

   ::

      0

      1
      Hello
      2
      HelloHello
      3
      HelloHelloHello
      Done!

#. The first time Python executes the ``for`` statement in line 1, ``num`` is
   assigned a value of ``0``.
#. Next, Python checks if the value of ``num`` is less than the value inside
   ``range``. Since ``num < 4`` evaluates to ``True``, the loop body executes.
#. Line 2 prints the current value of ``num``.
#. Line 3 prints the string ``Hello`` zero times.
#. Python reaches the end of the loop body (the indented lines). At this point,
   it increases the value of ``num`` by 1 and then MOVES BACK TO THE ``for``
   STATEMENT (line 1).
#. The new value of ``num`` (``1``) gets compared to the ``range`` value.
   Since ``num < 4`` still returns ``True``, the loop body executes again.
#. Lines 2 and 3 run with the new value of ``num``, so we see ``1`` and
   ``Hello`` printed to the console.
#. Python again reaches the end of the loop body, increases the value of
   ``num`` and moves back up to the ``for`` statement.
#. This process continues until the value of ``num`` reaches the end of the
   specified ``range``. Once the comparison ``num < 4`` returns ``False``, the
   loop ends. Since Python adds 1 after each iteration, this occurs when
   ``num`` is 4 (so ``4 < 4`` is ``False``). At that point, the loop body will
   have run exactly 4 times, with ``num`` taking the values 0, 1, 2, and 3.
#. Once the loop finishes, Python proceeds to line 5 and prints ``Done!`` one
   time.

We can use a picture to show the *flow of execution* of this ``for`` loop:

.. _for-loop-control-flow:

.. figure:: figures/for-loop-diagram.png
   :alt: Diagram showing the flow of a program with a for loop.

   Flow of execution of a ``for`` loop

Notice that even though line 1 uses ``range(4)``, the value ``4`` is NOT
included in the output. Why?

Begin Counting at 0
^^^^^^^^^^^^^^^^^^^

.. index:: ! zero-based indexing

Iterating a certain number of times is a very common thing to do, and Python
gives us the built-in ``range`` keyword to provide a set of values for the loop
variable to use.

The sequence provided by ``range`` always starts with ``0``. If you ask for
``range(4)``, then you will get 4 values starting with 0. In other words, 0, 1,
2, and finally 3. Notice that 4 is not included since we started with 0.
Likewise, ``range(10)`` provides 10 values, 0 through 9. Starting a count at 0
instead of at 1 is called **zero-based indexing** and is very common in
computer programming.

.. admonition:: Note

   Programmers like to count from 0!

   For ``range(n)``, the loop variable will take each integer value from 0 up
   to BUT NOT INCLUDING ``n``.

Check Your Understanding
------------------------

.. admonition:: Question

   How does python know what lines are contained in the loop body?

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, true)"> The lines are indented by the same amount from the <strong style="color:#419f6a">for</strong> statement.</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> There is always exactly one line in the loop body.</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> The loop body ends with an empty line.</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> The loop body ends at the next <strong style="color:#419f6a">for</strong> statement.</li>
      </ol>
      <p id="Q1"></p>

.. Answer = a.

.. admonition:: Question

   How many lines does the following code print?

   .. sourcecode:: python
      :linenos:

      for number in range(10):
         print("I have", 12 - number, "cookies. I'm going to eat one!")
   
   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> 1</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> 9</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, true)"> 10</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> 12</li>
      </ol>
      <p id="Q2"></p>

.. Answer = c.

.. admonition:: Question

   For the code above, what is the value of ``number`` the *third* time Python
   executes the loop?
   
   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, false)"> 1</li>
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, true)"> 2</li>
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, false)"> 3</li>
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, false)"> 4</li>
      </ol>
      <p id="Q3"></p>

.. Answer = b.

.. admonition:: Question

   For the same code, what is the LAST line printed by the program?
   
   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q4" autocomplete="off" onclick="evaluateMC(name, false)"> <code class="pre">I have 2 cookies. I'm going to eat one!</code></li>
         <li><input type="radio" name="Q4" autocomplete="off" onclick="evaluateMC(name, true)"> <code class="pre">I have 3 cookies. I'm going to eat one!</code></li>
         <li><input type="radio" name="Q4" autocomplete="off" onclick="evaluateMC(name, false)"> <code class="pre">I have 10 cookies. I'm going to eat one!</code></li>
         <li><input type="radio" name="Q4" autocomplete="off" onclick="evaluateMC(name, false)"> <code class="pre">I have 12 cookies. I'm going to eat one!</code></li>
      </ol>
      <p id="Q4"></p>

.. Answer = b.
