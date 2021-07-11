.. _exercises-functions:

Exercises: Functions
====================

To solve problems with code, you need to be able to break large
problems into small ones. Usually, these smaller problems will take the form of
functions that are used to solve the larger problem. Therefore, to solve problems with code, 
you need to be skilled at writing functions. And to master
functions, you need to write a *lot* of them.

These exercises ask you to write many relatively small functions, which
combine to form larger, more complicated ones.

At the end, you will be able to create strings of shapes, like this nifty
diamond:

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

There is no starter code for these exercises, so create a new Python project
at `repl.it <https://repl.it/login>`__ to get started.

Rectangles
----------

A. Write a function ``make_line(size)`` that returns a line with exactly ``size``
   hashes.

   .. sourcecode:: py

      print(make_line(5))

   **Console Output**

   ::

      #####

   :ref:`Check your solution <functions-exercise-solutionsA>`. 

#. Write a function called ``make_square(size)`` that returns a ``size`` by
   ``size`` string of hashes. The function should NOT print each row of the
   square. Instead, it must return a single string that contains the entire
   shape.

   .. admonition:: Tip
   
      #. Call your ``make_line`` function to create each row of the square.
      #. The newline character, ``\n``, will be helpful to you.
      #. Do NOT include a newline character at the end of your string.

   .. sourcecode:: py

      print(make_square(5))

   **Console Output**

   ::

      #####
      #####
      #####
      #####
      #####

   .. admonition:: Warning

      For each of the shape exercises, do not include a newline character at
      the very end of your string. While the final ``\n`` might not be
      noticeable for the simpler shapes, including it will make life harder for
      you toward the end of the exercises.

#. Write a function ``make_rectangle(width, height)`` that returns a
   rectangle with the given width and height. Use your ``make_line`` function to
   do this.

   .. sourcecode:: py

      print(make_rectangle(5, 3))

   **Console Output**

   ::

      #####
      #####
      #####

   :ref:`Check your solution <functions-exercise-solutionsC>`. 


#. Now, go back and rewrite ``make_square`` to use ``make_rectangle``.

Triangles
---------

E. Write a function ``make_downward_stairs(height)`` that prints the staircase
   pattern shown below, with the given height. Use your ``make_line`` function
   to do this.

   .. sourcecode:: py

      print(make_downward_stairs(5))

   **Console Output**

   ::

      #
      ##
      ###
      ####
      #####

   :ref:`Check your solution <functions-exercise-solutionsE>`.


F. Write a function ``make_space_line(numSpaces, numChars)`` that returns a line
   with exactly the specified number of spaces, followed by the
   specified number of hashes, followed again by ``num_spaces`` more spaces.

   .. sourcecode:: py

      print(make_space_line(3, 5));

   **Console Output**

   ::

      ___#####___

   .. note:: We have inserted underscores to represent spaces, so they are visible in the output. Don't do this in your code.

G. Write a function ``make_isosceles_triangle(height)`` that returns a triangle
   of the given height.

   .. sourcecode:: py

      print(make_isosceles_triangle(5))

   **Console Output**

   ::

          #
         ###
        #####
       #######
      #########

   .. tip:: Consider the top line of the triangle to be level 0, the next to be line 1, and so on. Then line ``i`` is a space-line with ``height - i - 1`` spaces and ``2 * i + 1`` hashes.

   :ref:`Check your solution <functions-exercise-solutionsG>`.

Diamonds
---------

H. Write a function ``make_diamond(height)`` that returns a diamond where the
   triangle formed by the *top* portion has the given height.

   .. sourcecode:: py

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

   .. tip::

      Consider what happens if you create a triangle and reverse it using
      :ref:`our reverse function <reverse_func>`.

Bonus Mission
--------------

Refactor your functions so that they take a single character as a parameter,
and draw the shapes with that character instead of always using ``'#'``. Make
the new parameter optional, with default value ``'#'``.