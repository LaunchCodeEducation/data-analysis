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

   import fun_shapes
   from fun_shapes import draw_polygon

Note that we do NOT need to include the ``.py`` extension when we import the
module.

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
