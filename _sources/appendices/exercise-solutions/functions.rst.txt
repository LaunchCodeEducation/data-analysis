Exercise Solutions: Functions
==============================

Part 1: Rectangles
-------------------

A. Write a function ``make_line(size)`` that returns a line with exactly ``size``
   hashes.

   .. sourcecode:: py

      def make_line(size):
         line = ""
         for i in range(size):
            line += "#"
         return line

      print(make_line(5))

   **Console Output**

   ::

      #####

   :ref:`Return to Exercises<exercises-functions-part1>`

   .. _exercises-functions-square:

#. Write a function called ``make_square(size)`` that returns a ``size`` by
   ``size`` string of hashes. 

   .. sourcecode:: py

      def make_square(size):
         square = ""
         for i in range(size):
            square += (make_line(size) + "\n")
         return square

      print(make_square(5))

   **Console Output**

   ::

      #####
      #####
      #####
      #####
      #####

   :ref:`Return to Exercises<exercises-functions-part1>`

   .. _exercises-functions-rectangle:
 
#. Write a function ``make_rectangle(width, height)`` that returns a
   rectangle with the given width and height. Use your ``make_line`` function to
   do this.

   .. sourcecode:: py

      def make_rectangle(width, height):
         rectangle = ""
         for i in range(height):
            rectangle += (make_line(width) + "\n")
         return rectangle

      print(make_rectangle(5, 3))

   **Console Output**

   ::

      #####
      #####
      #####

   :ref:`Return to Exercises<exercises-functions-part1>`

Part 2:  Triangles
------------------

.. _exercises-functions-stairs:

A. Write a function ``make_downward_stairs(height)`` that prints the staircase
   pattern shown below, with the given height. 

   .. sourcecode:: py

      def make_downward_stairs(height):
         stairs = ""
         for i in range(height):
            stairs += (make_line(i+1) + "\n")
         return stairs

      print(make_downward_stairs(5))

   **Console Output**

   ::

      #
      ##
      ###
      ####
      #####

   :ref:`Return to Exercises<exercises-functions-part2>`

   .. _exercises-functions-space-line:

#. Write a function ``make_space_line(numSpaces, numChars)`` that returns a line
   with exactly the specified number of spaces, followed by the
   specified number of hashes, followed again by ``num_spaces`` more spaces.

   .. sourcecode:: py

      def make_space_line(numSpaces, numChars):
         space_line = ""
         for i in range(numSpaces):
            space_line += " "
         for i in range(numChars):
            space_line += "#"
         for i in range(numSpaces):
            space_line += " "
         return space_line

      print(make_space_line(3, 5))

   **Console Output**

   ::

      ___#####___

   :ref:`Return to Exercises<exercises-functions-part2>`

   .. _exercises-functions-triangle:

#. Write a function ``make_isosceles_triangle(height)`` that returns a triangle
   of the given height.

   .. sourcecode:: py

      def make_isosceles_triangle(height):
         triangle = ""
         for i in range(height):
            triangle += (make_space_line(height - i - 1, 2 * i + 1) + "\n")
         return triangle

      print(make_isosceles_triangle(5))

   **Console Output**

   ::

          #
         ###
        #####
       #######
      #########

   :ref:`Return to Exercises<exercises-functions-part2>`

Part 3: Diamonds
----------------

.. _exercises-functions-diamond:

A. Write a function ``make_diamond(height)`` that returns a diamond where the
   triangle formed by the *top* portion has the given height.

   .. sourcecode:: py

      def make_diamond(height):
         diamond = ""
         triangle = make_isosceles_triangle(height)
         diamond += triangle[:-1]
         for i in range(len(triangle)-1, -1, -1):
            diamond += triangle[i]
         return diamond

      print(make_diamond(5))

   **Console Output**

   ::

          #
         ###
        #####
       #######
      #########
      #########
       #######
        #####
         ###
          #

.. TODO: Check functions chapter for reverse function.

   .. admonition:: Tip

      Consider what happens if you create a triangle and reverse it using
      our reverse function.

:ref:`Return to Exercises<exercises-functions-part3>`

Optional Mission
----------------

Refactor your functions so that they take a single character as a parameter,
and draw the shapes with that character instead of always using ``'#'``. 

.. sourcecode:: python

   def make_line(size, char):
      line = ""
      for i in range(size):
         line += char
      return line

   print(make_line(8, '&'))


**Console Output**

::

   &&&&&&&&

:ref:`Return to Exercises<exercises-functions-bonus>`

Make the new parameter optional, with default value ``'#'``.

.. sourcecode:: python

   def make_line(size, char = "#"):
      line = ""
      for i in range(size):
         line += char
      return line

   print(make_line(8))

**Console Output**

::

   ########

:ref:`Return to Exercises<exercises-functions-bonus>`