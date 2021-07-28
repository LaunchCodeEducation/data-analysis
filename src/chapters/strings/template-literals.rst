Template Literals
=================

.. index:: concatenation

Earlier, we used *concatenation* to
:ref:`combine strings and variables together <string-concatenation>` in order
to create a specific output:

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      name = 'Jack'
      current_age = 9

      print("Next year, " + name + " will be " + str(current_age + 1) + ".")

   **Console Output**

   ::

      Next year, Jack will be 10.

   Note the following:
   
   #. We must include spaces inside each of the strings to make the output
      readable. Without the spaces, line 4 prints ``Nextyear,Jackwillbe10.``
   #. In order to concatenate, we must convert the ``int`` value from the
      expression ``current_age + 1`` into the ``str`` data type.

While it does work, concatenation quickly gets tedious for any output that
depends on multiple variables. Also, concatenation usually requires several
test runs of the code in order to check for syntax errors and proper spacing.
Fortunately, Python offers us a better way to accomplish the same thing.

.. index:: ! template literal

**Template literals** allow for the automatic insertion of expressions and
variable values into strings.

Within a template literal, type the string, but leave *placeholders* where you
want to insert values. Placeholders are identified by a pair of curly braces,
``{}``. When the program runs, the placeholders are replaced by the values we
want to include in the string.

Let's compare the string concatenation in the example above to a template
literal:

.. sourcecode:: python

   # Concatenation (messy, complicated, hard to read)
   "Next year, " + name + " will be " + str(current_age + 1) + "."

   # Template literal (beautiful, simple, easier to read)
   "Next year, {} will be {}."

The braces ``{}`` indicate where we want to insert the values for ``name`` and
``current_age + 1``. Note how we only need one pair of quotes, and the spacing
fits naturally around the ``{}``. Python also takes care of any data type
conversions.

.. index:: ! format method

.. _format-string-method:

The ``format()`` Method
-----------------------

Template literals allow us to insert variables and other expressions directly
into strings. To accomplish this, we need:

#. A string that includes curly braces ``{}``.
#. The ``.format()`` method.
#. A value to insert into each set of braces.

The general syntax is:

.. sourcecode:: python

   string_with_braces.format(value_1, value_2, etc.)

The values inside ``format()`` can be numbers, strings, variables, or expressions.

.. admonition:: Example

   Compare the difference between printing ``output`` by itself vs. printing
   ``output.format()``.

   .. sourcecode:: python
      :linenos:

      name = 'Jack'
      current_age = 9
      output = "Next year, {} will be {}."

      print(output)
      print(output.format(name, current_age + 1))

   **Console Output**

   ::

      Next year, {} will be {}.
      Next year, Jack will be 10.

Python works from left to right through the string, replacing each placeholder
with the next value inside ``format()``.

.. admonition:: Try It!

   Experiment with the ``format()`` string method.

   #. Run the program several times with different values for ``my_string`` and
      ``my_number``.
   #. Change the order of ``my_number`` and ``my_string`` inside the ``format``
      parentheses. What happens?
   #. Change the location of one set of ``{}`` in ``output``. What happens?
   #. Remove one set of ``{}`` from ``output`` and run the program. What
      happens?
   #. Use four or more ``{}`` inside ``output`` and run the program. What
      happens?

   .. replit:: python
      :slug: FormatPractice
      :linenos:

      my_string = 'Hello'
      my_number = 3
      my_expression = my_string * my_number

      output = '''This is my_string: "{}". 
      This is a my_number: {}.
      This is the length of my_string * my_number: {}'''

      print(output.format(my_string, my_number, len(my_expression)))

.. admonition:: Note

   Python fills the empty braces ``{}`` from left to right through the string,
   and it uses the values given in ``format`` from left to right as well.

   A mismatch between the number of braces in the string and the number of
   values in ``format`` will NOT throw an error. However, the output will not
   look the way you want.

Index Values with ``format()``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

What if we want to use the same value multiple times in a string?

.. admonition:: Example

   Let's take the case where we add a number to itself three times:

   .. sourcecode:: python

      my_num = 10
      output = '{} + {} + {} = {}'

      print(output.format(my_num, my_num, my_num, 3*my_num))

   **Console Output**

   ::

      10 + 10 + 10 = 30

Remember that when we code, we want to avoid repeating ourselves as much as
possible. Typing ``my_num`` three times inside ``format()`` should set off
alarm bells in our heads. There is a shorter way.

.. index:: ! indices

We can include index values inside of the curly braces ``{}``. 
These **indices** (a plural of index)
refer to the items inside ``format()``, and the indexes begin with 0.
Zero-based counting strikes again!

.. admonition:: Example

   Let's add index values to the template literal:

   .. sourcecode:: python

      my_num = 10
      output = '{0} + {0} + {0} = {1}'

      print(output.format(my_num, 3*my_num))

   **Console Output**

   ::

      10 + 10 + 10 = 30

When Python evaluates ``{0}``, it inserts the *first* value from ``format()``.
``{1}`` gets replaced by the second value. Since ``{0}`` occurs three times,
``my_num`` is used for each one.

If we add another value inside ``format()``, we can insert it into the string
by adding ``{2}`` to ``output``.

Index values in template literals are flexible. The order of the values in curly
braces does not need to match the order of the values within ``format()``.

.. admonition:: Example

   .. sourcecode:: python

      output = "Hello, {1}. You turn {0} years old today. Happy birthday, {1}!"

      print(output.format(5, 'Anna'))

   **Console Output**

   ::

      Hello, Anna. You turn 5 years old today. Happy birthday, Anna!

Notice how the string ``'Anna'`` is used first in the print statement, even though it
comes second within ``format()``.

.. admonition:: Tip

   Even if you do not think you will need indicies in a template literal, it is
   a good idea to use them anyway!

   In this book, most of the template literals used in the examples and starter
   code will contain index values.

f-Strings
---------

.. index:: ! f-string

Python versions 3.6 and later provide another way to insert values and
expressions into a string. The new format is called an **f-string**, for
*format string*.

.. sourcecode:: python

   f"This is a string with a {name}, an {age}, and a calculated result, {3+2*10}."

Items to note:

#. f-strings begin with the character ``f``, followed by the string in quotes.
#. Instead of index values, variable names or expressions are placed inside the
   curly braces ``{}``.

.. admonition:: Example

   Let's refactor an earlier example to use an f-string:

   .. sourcecode:: python
      :linenos:

      name = 'Jack'
      current_age = 9
      output = f"Next year, {name} will be {current_age + 1}."

      print(output)

   **Console Output**

   ::

      Next year, Jack will be 10.

Essentially, ``f`` replaces ``.format``, and using variable names and/or
expressions inside the braces replaces the index values. When Python comes
across an ``f`` in front of a string, it evaluates everything within the curly
braces and inserts the results into the string.

.. admonition:: Note

   We won't discuss f-strings further in this book. If you are interested in
   digging deeper, here are a couple of places to start:

   #. `Python String Formatting Best Practices <https://realpython.com/python-string-formatting/>`__,
   #. `Python 3's f-Strings <https://realpython.com/python-f-strings/>`__.

Check Your Understanding
------------------------

.. admonition:: Question

   Mad Libs are games where one player asks a group to supply random words
   (e.g. "Give me a verb," or, "I need a color"). The words are substituted
   into blanks within a story, which is then read for everyone's amusement. 

   Refactor the following code to replace the awkward string concatenation with
   a template literal. Be sure to add your own choices for the variables!

   Feel free to use either ``.format()`` or an f-string.

   .. replit:: python
      :slug: MadLibConceptCheck
      :linenos:

      # Refactor the string concatenation to use either .format() or an f-string instead.
      plural_noun = ''
      name = ''
      verb = ''
      adjective = ''
      color = ''

      mad_lib = "Python provides a "+ color +" collection of tools — including " + adjective + " syntax and " + plural_noun + " — that allows "+ name +" to "+ verb +" with strings."

      print(mad_lib)