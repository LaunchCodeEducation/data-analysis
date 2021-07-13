Calling Functions
=================

.. index::
   single: function; call

**Calling a function** is the act of running that function and giving it the
information it needs to do its job.

Making a Function Run
---------------------

The general syntax for calling a function is:

::

   function_name(input values)

You have already become familiar with several Python functions:

- ``print()``
- ``len()``
- Type conversion functions like ``int()``, ``str()``, and ``list()``
- String and list methods, such as ``find()`` or ``reverse()``.

Every function works in the same way. By typing the function's name, followed by
parentheses, we *call* the function. This results in an action being carried
out.

Sometimes, we include values inside the parentheses. When we do this, the
function carries out its action with that data.

.. admonition:: Example

   The *action* of the ``print`` function displays information to the console,
   while the ``int`` function returns the integer value from the given input.

   .. sourcecode:: python

      print("Hello, World!")
      num = int("23")
      print(num)

   **Console Output**

   ::

      Hello, World!
      23

As programmers, we do not need to know *how* Python prints to the console or
converts a string to an integer. Instead, we just need to be able to ask Python
to do those jobs for us with the data we supply.

.. admonition:: Note

   .. index:: ! argument
   
   **Arguments** refer to the data values we send to a function. Some functions
   do not require arguments inside the parentheses, ``()``.

If a function requires more than one argument, we separate them with commas:

::

   function_name(argument_1, argument_2, ...)