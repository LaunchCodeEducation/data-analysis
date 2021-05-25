Iteration Improves the Turtle Program
=====================================

Take another look at the turtle code for drawing a square. Which statements are
repeated? How many times?

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

We can *DRY* the code by using a ``for`` loop. Complete the code below by
entering a value into ``range``. Next, copy and paste the SMALLEST number of
statements into the loop body that will make the turtle draw a square. Don't
forget to indent!

.. raw:: html

   <iframe height="450px" width="100%" src="https://repl.it/@launchcode/LCHS-Turtle-Square?lite=true" scrolling="no" frameborder="yes" allowtransparency="true"></iframe>

Nice! By adding a loop, you were able to use only 3 lines of code to draw a
square instead of the original 8.

While “saving some lines of code” might be convenient, it is NOT the big deal
here. What is much more important is that we found a *repeating pattern* of
statements, and we changed our program to repeat the pattern.

Finding repeatable chunks of code and building our programs around those
chunks is a vital skill for coding.

How About Drawing Other Shapes?
-------------------------------

What if we want the turtle to draw a triangle instead of a square? Note that
``range(4)`` made the loop run 4 times and produced 4 lines. It seems
like we can change the value in ``range`` to make other shapes.

For a triangle, let's try replacing ``range(4)`` with ``range(3)`` to make 3
sides instead of 4:

.. admonition:: Example

   .. raw:: html

      <iframe height="600px" width="100%" src="https://repl.it/@launchcode/LCHS-Turtle-Polygons?lite=true" scrolling="no" frameborder="yes"></iframe>

Hmmm... that didn't quite work. This is because of line 7. ``bob.left(90)``
works fine for the square (all right angles), but the turtle needs to turn by a
different amount for a triangle.

Without getting deep into the geometry here, the answer is... 120 degrees!
Replace ``90`` with ``120`` and then run the program again.

Now Add Variables!
^^^^^^^^^^^^^^^^^^

We built one ``for`` loop to draw a square and a separate ``for`` loop to draw
a triangle. However, both loops do essentially the same thing---move the turtle
and then turn the turtle.

Rather than coding separate loops for every possible polygon (triangle, square,
pentagon, hexagon, etc.) we should DRY the loop! By using variables instead of
specific numbers inside ``range`` and ``left()``, we can make ONE loop that
works for ALL polygons.

Make the following adjustments in the editor above:

#. Before the loop, define a variable called ``num_sides`` and assign it a
   value. This stores the number of sides of the shape we want to draw.
#. Also before the loop, define a variable called ``turn_angle``. This stores
   the number of degrees that the turtle needs to rotate after drawing each
   side.
#. ``turn_angle`` needs to be calculated. Set
   the variable equal to ``360.0 / num_sides`` (360.0 degrees divided by the
   number of sides). If you want to know why this works, go ask your math
   teacher! They will LOVE to explain it to you.
#. Replace the number in ``range`` with the variable ``num_sides``.
#. Replace the number in ``left`` with ``turn_angle``.
#. Test the program by having it draw a square first (``num_sides = 4``), then
   change ``num_sides`` to make a triangle.
#. Ever wanted to know what a *nonagon* looks like (9 sides)? How about a
   `triskaidecagon <https://en.wikipedia.org/wiki/Tridecagon>`__? Change the
   value of ``num_sides`` to find out!

.. admonition:: Tip

   If you have your own repl.it account, you can save a copy of the finished
   polygon loop by logging in and *forking* the `final code <https://repl.it/@launchcode/LCHS-Turtle-Polygons-Solution>`__.
