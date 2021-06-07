Exercises: Functions
====================

If your teacher added you to a :ref:`Trinket course <trinket-course-assignments>`, complete the exercises
there.

Otherwise, use the links below to code in your own free account.

.. admonition:: Note

   The code editors embedded in the exercises all include a link to repl.it in
   the upper right corner. For the matching Trinkets, click these links:

   #. `Exercises 1 & 2 <https://trinket.io/python/312522b320?showInstructions=true>`__
   #. `Exercise 3 <https://trinket.io/python/497b5293b3?showInstructions=true>`__
   #. `Exercise 4 <https://trinket.io/python/accbf508b3>`__
   #. `Exercise 5 <https://trinket.io/python/6e523d6464>`__
   #. `Exercises 6 - 8 <https://trinket.io/python/531698b16b?showInstructions=true>`__

.. _functions-turtle-exercises:

Part A: More Turtles
--------------------

#. Use a loop and the ``draw_square`` function we wrote
   :ref:`in this chapter <draw-square-code>` to draw the image shown below.
   Make each side 30 units long, and note that the turtle moves away from the
   last square.
   
   (Check the :ref:`Turtle Appendix <turtle-guide>` if you need to review the
   turtle methods).

   .. figure:: figures/exercise-1-image.png
      :alt: Image showing 5 squares evenly spaced in a row, with the turtle off to the right of the last shape.

   .. raw:: html

      <iframe height="600px" width="100%" src="https://repl.it/@launchcode/Functions-Exercise-1?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

#. In the editor above, define a new function called ``draw_polygon`` that
   takes 3 parameters---a turtle object, a number of sides, and the length of
   each side. Place the new function in the lines before
   ``bob = turtle.Turtle()``.

   *Hint*: You drew polygons as part of the 
   :ref:`Turtle Project <draw-polygon>` in the Loops chapter.

   After you finish coding the function, replace the ``draw_square`` function
   call in the loop with ``draw_polygon`` to produce a row of shapes.

   .. figure:: figures/exercise-2-image.png
      :alt: Image showing 5 identical shapes evenly spaced in a row, with the turtle off to the right of the last shape.

      Two possible outcomes from using ``draw_polygon``.

   .. admonition:: Try It!

      Just for fun, modify your loop code to produce shapes with different
      colors, sizes, or sides.

      .. figure:: figures/exercise-2b-image.png
         :alt: Images showing three rows of shapes with different: 1) colors, 2) sizes, 3) number of sides.

#. Write a function called ``draw_sprite`` that draws a figure like the one
   shown below. The function needs parameters for the turtle, the number of
   legs, and the length of the legs.

   .. figure:: figures/exercise-3-image.png
      :alt: Image showing a sprite with 7 legs and the turtle shape at the center.
   
   Call the function to create a sprite with 10 legs of length 115.

   .. raw:: html

      <iframe height="550px" width="100%" src="https://repl.it/@launchcode/Functions-Exercise-3?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

   .. admonition:: Try It!

      Add a parameter to ``draw_polygon`` called ``fancy_corners``. If
      ``True``, then the function should call ``draw_sprite`` at each corner of
      the shape. Make the sprite legs half the length of each side.

      .. figure:: figures/exercise-3b-image.png
         :alt: Image showing a sprite with 7 legs and the turtle shape at the center.
         :scale: 80%

Part B: Return Values
---------------------

4. Write a ``shift_case`` function that takes a single string parameter and
   returns a different string. The function should loop through the string and
   change uppercase characters to lowercase, and lowercase to uppercase.

   For example, for the argument ``'Hello, World!'``, the function returns
   ``'hELLO, wORLD!'``.

   .. raw:: html

      <iframe height="500px" width="100%" src="https://repl.it/@launchcode/Functions-Exercise-4?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

#. Write a ``calculate_average`` function that uses a list of numbers as the
   parameter. The function should find and return the average of the numbers
   from the list. Use the ``round()`` function to return an average rounded
   to one decimal place.

   Sample results:

   a. num_list = [2, 7, 6], average = 5.0
   b. num_list = [20, 17, 46, 8], average = 22.8
   c. num_list = [0, 3.33, 44, 50, 63, 70.9, 75.2, 83.2], average = 48.7

   .. admonition:: Note

      average = (sum of the elements in list) / (number of elements in list)

   .. raw:: html

      <iframe height="500px" width="100%" src="https://repl.it/@launchcode/Functions-Exercise-5?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

#. Write a function ``make_line(num_chars, symbol)`` that returns a line with
   exactly ``num_chars`` symbols. ``num_chars`` will be an integer, and
   ``symbol`` will be a character. Note that the function must *RETURN* a
   string, not print it!

   If the function call does not provide an argument for ``symbol``, use the
   default character ``'#'``.

   .. sourcecode:: python

      print(make_line(5, 'T'))
      print(make_line(8))

   **Console Output**

   ::

      TTTTT
      ########
   
   .. raw:: html

      <iframe height="500px" width="100%" src="https://repl.it/@launchcode/Functions-Exercise-6?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

#. In the editor above, add a function called ``make_rectangle`` that returns a
   rectangle string with a given width, height, and symbol. The function should
   NOT print each row of the rectangle. Instead, it must return a single string
   that contains the entire rectangle shape.
   
   .. admonition:: Tips
   
      #. Call your ``make_line`` function to create each row of the rectangle
         string.
      #. The newline character, ``\n``, will be helpful to you.
      #. Do NOT include a newline character at the end of your string.
      #. Use ``'#'`` as the default symbol.

   .. sourcecode:: python

      print(make_rectangle(5, 3))
      print(make_rectangle(2, 4, '*'))

   **Console Output**

   ::

      #####
      #####
      #####
      **
      **
      **
      **

#. In the same editor, code a ``make_square`` function that calls
   ``make_rectangle``. The function should behave something like this:

   .. sourcecode:: python

      print(make_square(4))
      print(make_square(3, 'Rutabaga'))

   **Console Output**

   ::

      ####
      ####
      ####
      ####
      RutabagaRutabagaRutabaga
      RutabagaRutabagaRutabaga
      RutabagaRutabagaRutabaga

Bonus Exercises
---------------

#. Add a ``draw_spiral`` function to one of the turtle editors to produce
   either of the following shapes. *Hint*: The function needs a turtle, an
   angle, a starting line length and the number of lines to draw.

   .. figure:: figures/turtle-spirals.png
      :alt: Image showing two spiral shapes produced by the ``draw_spiral`` function.

      The spiral on the left uses an angle of 90°, while the one on the right
      uses an angle of 89°.

#. Add functions to the editor in part B, exercise 6 to produce any of the
   following shapes:

   ::

      #                       ##
      ##                     ####
      ###                   ######
      ####                 ########
      #####               ##########

      #
      ##
      ###
      ###
      ##
      #
