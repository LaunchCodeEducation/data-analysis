Using a Class
=============

Classes provide a pattern for making new objects.

Every object is an *example of* its class, but the object is NOT a copy of the
class. We use a class to *build* objects, just like we use a cutter to shape
separate cookies. The cookie and the cutter are NOT the same thing.

Create New Objects
------------------

.. index:: ! instance

To create an object from a class, the general syntax is:

.. sourcecode:: python

   object_name = ClassName(arguments)

This creates an **instance** of the class, which means ``object_name`` has the
same set of property names as every other object made from the class. However,
the *values* for the properties may differ between objects.

.. admonition:: Try It!

   Let's use a ``Student`` class to create two objects. Run the following
   program an examine the output.

   .. raw:: Html

      <iframe src="https://trinket.io/embed/python3/56e2b29d76" width="100%" height="300" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

In lines 7 and 8, we call the ``Student`` class twice and pass in different
sets of arguments, creating the objects ``dan`` and ``jessi``.

The output of line 10 shows that ``dan`` and ``jessi`` are both the same type
of object (``Student``). Line 11 shows us that the two share the same property
names (like ``id``), but they have different values assigned to those names.

After creating a ``Student`` object, we can access, modify, or add new
properties and values as described in the
:ref:`Object Properties <object-properties>` section.

.. admonition:: Try It

   Play around with :ref:`modifying and adding properties <object-properties>`
   inside and outside of the ``Student`` class.

   #. Add a new property inside the ``__init__`` method.
   #. On line 12, change the value of the ID number for ``dan``, then print the
      new information.
   #. On line 15, add the ``act_score`` property to ``jessi`` and assign it an
      integer value. Print this value to check your work.

   Note that line 15 adds the ``act_score`` property to the ``jessi`` object,
   but this change does NOT affect any other objects created with ``Student``.

.. admonition:: Note

   Did you ever wonder why we needed to type "turtle" 3 times to create a new
   turtle object? Now that we know how to call a class, we can see why this is
   necessary!

   .. sourcecode:: python
      :linenos:

      import turtle

      bob = turtle.Turtle()

   #. Line 1 imports the ``turtle`` module, which contains all the code related
      to these objects AND the class for making them.
   #. Line 3 tells the program, *Look in the* ``turtle`` *module and call the*
      ``Turtle()`` *class*. The class code executes, creates a new ``turtle``
      object, and assigns it to the variable ``bob``.

Default Property Values
^^^^^^^^^^^^^^^^^^^^^^^

If we try to create a new ``Student`` object without passing in all of the
required arguments, the program crashes.

To avoid issues with missing arguments, we can set a *default* value for a
parameter as follows:

.. sourcecode:: python
   :linenos:

   class Student:
      def __init__(self, name, grade, id_number = 'Missing'):
         self.name = name
         self.grade_level = grade
         self.id = id_number

Now if we call ``Student`` but leave out an ID number, the ``__init__`` method
automatically assigns ``id`` a value of ``'Missing'``. If we include an
argument for ``id_number``, then the default value is ignored.

.. admonition:: Try It!

   Return to the example above and modify the ``Student`` class to use a
   default value for one or more of the ``__init__`` parameters.

Another Mental Image for Classes
--------------------------------

Besides the cookie cutter idea, we can also think of a class as a *factory for
making objects*. The ``Student`` class itself isn’t an instance of a student,
but it contains all the tools to make student objects. Every time we call the
class, we ask the factory to make a new object. As the object goes through the
production line, the ``__init__`` method runs to get the object properly set
up.

The statement ``jessi = Student('Jessi', 12, 3333)`` essentially says,
*Hey, Student factory! Please make me a new object with these settings*.
