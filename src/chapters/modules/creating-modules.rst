.. _custom-modules:

Creating Modules
================

Up until now, we have imported modules that are already part of the Python
libraries. Now let's look at how to define our own modules and save them
in a form we can use in other programs.

Create a New Python File
------------------------

The first step in making a module is to decide which values and functions
belong in that module. These should all perform similar tasks and/or be related
to each other in some way.

For example, let's assume we want to create a module called ``turtle_shapes``.
Functions like ``draw_square``, ``draw_polygon``, and ``draw_sprite`` would be
good choices to put in the module, but something like
``calculate_average_grade`` definitely does NOT belong.

The next step is to open a new file in our code editor and give it a name that:

#. begins with a letter and contains only lowercase letters,
#. is as short as possible but still descriptive,
#. separates words with an underscore ``_``,
#. ends with the extension ``.py`` (for example, ``turtle_shapes.py``).

.. admonition:: Note

   The ``.py`` extension tells a code editor that the contents of the file
   follow the Python programming syntax.

Finally, we add the functions and values we want in the module. We code these
just like any other program, with ``import`` statements first, then function
definitions, then variable assignments.

That's pretty much it. Once we save the file, we can use the syntax we learned
to import the entire module or specific parts of it into another program:

.. sourcecode:: Python

   import turtle_shapes
   from turtle_shapes import draw_polygon

Note that we do NOT need to include the ``.py`` extension when we import the
module.

Let's build a module to practice this process.

Setting Turtle Properties
-------------------------

You probably noticed that every time we use a turtle in an example or exercise,
we include a set of statements that define properties for that turtle:

.. admonition:: Example

   Count the number of "prep" steps we need before our turtle draws its first
   line:

   .. sourcecode:: Python
      :linenos:

      import turtle

      bob = turtle.Turtle()
      bob.color('blue')
      bob.shape('turtle')
      bob.pensize(3)
      bob.speed(8)

      bob.circle(75)

   Line 3 creates the new turtle object, called ``bob``. Lines 4 - 7 set the
   properties, and line 9 finally draws something on the screen.

It takes one line of code to set each of the properties for a turtle. If we
need to define multiple turtles, this gets tedious really fast.

We can help ourselves by moving the setup code into a pair of functions, and
then calling those functions for each new turtle:

.. admonition:: Example

   By including some default values, we can call the ``create_new_turtle``
   function with no arguments, with values for some of the properties, or
   with arguments for each property.

   .. sourcecode:: Python
      :linenos:

      import turtle

      def create_new_turtle(t_color='black', t_shape='turtle', t_pen=3, t_speed=8):
         turtle_name = turtle.Turtle()
         set_turtle_properties(turtle_name, t_color, t_shape, t_pen, t_speed)
         return turtle_name

      def set_turtle_properties(t_name, t_color='black', t_shape='turtle', t_pen=3, t_speed=8):
         t_name.color(t_color)
         t_name.shape(t_shape)
         t_name.pensize(t_pen)
         t_name.speed(t_speed)

      bob = create_new_turtle()
      lin = create_new_turtle('purple', 'square')

This is better, since it reduces the repetition in the program. However, if we
want to use this shortcut in ALL of our turtle programs, we need to create a
module to hold the code.

Create the ``turtle_prep`` Module
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

In the editor below, notice that there are two file tabs open---``main.py`` and
``turtle_prep.py``. The first file contains the code that directs what gets
drawn on the screen. The second file is currently empty, but it will eventually
hold all of the setup steps to get each turtle ready.

Follow these instructions to create the ``turtle_prep`` module:

#. Run the program as-is to see how it works.
#. Click on the ``turtle_prep.py`` tab to access the editor for that file.
   (The workspace should be empty).
#. Return to ``main.py``. *REMOVE* lines 1 - 12 from ``main.py`` and paste them
   into ``turtle_prep.py``.
#. In ``main.py``, add the statement ``import turtle_prep`` on line 1.
#. Use dot notation to update ``bob = create_new_turtle()`` to
   ``bob = turtle_prep.create_new_turtle()``. Do the same for ``lin``.
#. Click *Run* to verify that the program still works.
#. Change the arguments in the ``create_new_turtle`` function calls to see how
   that affects the drawing.
#. In ``main.py``, call the ``set_turtle_properties`` function to change the
   properties of the turtles after they draw the circles. Add a new line or
   shape to check your work.

.. raw:: html

   <iframe src="https://trinket.io/embed/python/02c9ec9aef" width="100%" height="500" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Cool, we now have a set of code that we can pull into future turtle projects!

.. _module-location:

File Locations
--------------

One important thing to note is that when we import a module into a program,
Python needs to know exactly where to find that file.

When Python reads ``import module_name``, it first checks to see if the module
is one of the built-in Python files. Python knows exactly where these modules
are stored on our device, so the import occurs easily.

If a built-in module is not found, Python looks in the current *directory*,
which is the folder that holds the main program. If it finds a
``module_name.py`` file, it imports that into the program.

If the module is NOT in the same folder, Python expands its search to a larger
list of directories. This is a more complicated process, and it requires the
programmer to either save the new module in one of these directories or give
Python a detailed *path* to follow.

We will learn more about navigating different paths much later in the course.
For now, we will keep things simple by saving new modules in the same location
as ``main.py``.

Try It!
-------

Let's add another module to our turtle program.

In the editor above, click on the *New File* button to the right of the file
tabs. Name the new file ``turtle_shapes.py``.

.. figure:: figures/trinket-new-tab-button.png
   :alt: Image showing the location (upper right corner) of the New File button in the code editor.

   New File button.

#. Open the ``turtle_shapes.py`` tab and enter ``import turtle`` on line 1.
#. Paste in copies of the ``draw_square``, ``draw_polygon``, and
   ``draw_sprite`` functions you created in the
   :ref:`last chapter <functions-turtle-exercises>`. Be sure to include only
   the function code and NOT any turtle drawing commands.
#. In ``main.py``, import the ``turtle_shapes`` module.
#. Instead of the circle, have ``bob`` draw a different shape. Use dot notation
   to call one of the functions from ``turtle_shapes``. Make sure you include
   the required arguments in the proper order.
