Defining Our Own Functions
==========================

Built-in functions in Python give us a lot of capabilities. We gain even more coding potential by 
writing our own functions.

.. index::
   single: function; definition
   single: function; syntax
   single: function; named

We’ll start by looking at the general syntax.

.. _function-syntax:

Function Syntax
---------------

To create a function, use the following syntax:

.. sourcecode:: Python
   :linenos:

   def function_name( parameters ):
      # Code statements...

.. index:: ! def

``def`` is a keyword that instructs Python to create a new function.

.. index::
   single: function; name

Following ``def`` is the **function name**, which is the label that Python
attaches to the code. When writing our own functions, the programmer chooses the function name. Like any 
other variable, a function name should describe the purpose of the function. The stronger we make the name,
the less confusion we add to our code. A list of good naming practices appears
in the next section.

.. index::
   single: function; parameter

.. index:: ! parameter

Following the function name, we define **parameters** within the parentheses.
Parameters are variables that can only be used within the function itself. We
can define a function with one parameter, multiple parameters, or no parameters
at all.

The number and names of the parameters depends on what we want the function to
do. Parameters specify what information, if any, the function needs in order to
do its job.

The ``def`` statement ends with a colon.

.. _function-naming-rules:

Naming Functions
^^^^^^^^^^^^^^^^

Python function names should follow these rules:

#. Names CANNOT match any Python keyword like ``print`` or ``for``.

   .. admonition:: Tip
   
      Most code editors use syntax highlighting to indicate keywords. Paying
      attention to the highlighting helps avoid this naming mistake.

#. Names use only lowercase letters.
#. The name should describe exactly what the function does.

   .. admonition:: Tip
   
      You should prefer *long, descriptive names* over *short, abbreviated names*.
      If someone unfamiliar with your code can read the function name and tell
      you what it does, then you chose a good name.

#. For names with multiple words, separate the words with underscores (e.g.
   ``convert_score_to_percentage``).

.. admonition:: Examples

   **Good**

   - ``convert_feet_to_meters``
   - ``is_valid_number_entry``
   - ``draw_square``

   **Not Good**

   - ``convert``
   - ``is_valid``
   - ``draw``

Function Code
-------------

.. index::
   single: function; body

After the ``def`` statement comes the **function body**. This is where we code
the action that the function carries out. The function body can contain any
amount of code (statements, loops, conditionals, etc.), but the lines must be
indented when compared to the ``def`` keyword. Python recognizes the end of the
function body once it finds the first *unindented* line after the ``def``
keyword.

.. admonition:: Example

   .. sourcecode:: Python
      :linenos:

      def add_numbers_together(num):
         total = 0
         while num < 100:
            total += number
            number +=1
         
         return total

      print("Hello, World!")

   Line 1 defines the function name and parameter. Lines 2 - 6 are part of the
   function body. Line 8 is even with the ``def`` keyword, so it is NOT part of
   the ``add_list_numbers`` function.

Defining vs. Calling
--------------------

When we *define* a function, we make it available for later use. However, a
function does NOT run when it is defined. It must be *called* in order to
execute.

.. admonition:: Warning

   This is not only a common point of confusion for new programmers, but it can
   also cause logic errors!

Check Your Understanding
------------------------

.. admonition:: Question

   What are the *parameters* of the following function? Click *ALL* that apply.

   .. sourcecode:: Python
      :linenos:

      def perimeter_of_square(side_length):
         return side_length * 4
      
      print(perimeter_of_square(4))

   a. ``perimeter_of_square``
   b. ``side_length``
   c. ``print``

.. Answer = b

.. admonition:: Question

   For the same code sample, what are the *arguments* sent by the function call?
   Click *ALL* that apply.

   a. ``square``
   b. ``side_length``
   c. ``4``

.. Answers = c

.. admonition:: Question

   True or False: A function can be run several times by placing the function
   call inside a loop. 

   a. True
   b. False

.. Answer = a

.. admonition:: Question

   Which is the BEST name for the following function?

   .. sourcecode:: python
      :linenos:

      def func_name(radius):
        area = 3.14159 * radius**2
        return area

   a. ``area``
   b. ``calculate_area_of_circle``
   c. ``circle``
   d. ``shape``

.. Answer = b

