Classes
=======

Let's return to the ``type()`` function for a moment. It returns the data type
for the argument inside the parentheses, and we can print this information to
the console.

The code below prints the data types for several different values.

.. sourcecode:: python
   :linenos:

   #!/bin/python3

   print(type(12))
   print(type("Hello, World!"))
   print(type(['dog', 'cat', 'fish', 3.14]))

::

   <class 'int'>
   <class 'str'>
   <class 'list'>

Note how each data type gets reported after the word ``class``.

.. index:: ! class

As we saw before, objects have both *properties* and *methods*. All string
values (objects) share a set of properties and methods, while list objects hold
a different set. When two objects share a set of properties and methods, we say
they belong to the same **class**.

Classes allow us to organize the same type of data into the same group. For
example, all whole numbers are part of the ``int`` class, and any data enclosed
in quote marks belongs to the ``str`` class.

Every object belongs to a particular class, and this determines what the object
can do. The list ``['dog', 'cat', 'fish']`` CANNOT use any of the methods defined for
the ``str`` class, but it CAN use all of the available ``list`` methods.

Python defines many classes for us and makes them available for our use. In
each of the previous chapters, we've studied some of the ready-made
classes, like ``int``, ``str``, ``float``, ``bool``, ``list``, and ``dict``.

Objects Have a Data Type
------------------------

When we introduce a new value in our code, Python automatically identifies its
data type and groups it into a class.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      i_can_code = True

      print(type(i_can_code))

   **Console Output**

   ::

      <class 'bool'>

Every value has a data type, and each data type belongs to a class.

   Python treats every data value as an object.

Since Python treats every value as an object, *all objects have a data type,
and all objects belong to a class*.

On the previous page, we used the ``dog`` object. It contains both ``int`` and
``str`` properties (``age`` and ``name``), and it uses methods that don't
belong with any other data type. How should Python group it?

User Defined Classes
--------------------

Recall that Python gives us plenty of ready-made functions to help us code,
like ``print()``, ``max()``, and ``sum()``. We can also import more functions
from modules like we did with the :ref:`string module<string-module>`. 
However, these functions cannot do all the jobs we need. Our real
strength as programmers comes when we define our *own* functions. We can think
about classes in a similar way.

Sometimes, none of the given Python classes work for what we need to do. On the
previous page, the idea was to use an object that behaved differently from
strings, lists, etc. ``dog`` introduced a new data type, but Python does NOT
come with a pre-defined class for ``dog``.

Just like creating our own functions, Python allows us to define our own
*custom classes*. For the examples on the previous page, we defined a new
class and gave it the properties and methods it needed to describe the ``dog``
object.

On the next few pages, we will explore how to define a new class, create
objects from it, and learn why we want to do this.
