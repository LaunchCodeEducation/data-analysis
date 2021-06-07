Function Output
===============

Now that we have examined arguments and parameters in more detail, let's take a
look at the other end of the function machine---*output*.


.. index:: ! return

When we call a function, we often send one or more arguments *to* that
function. Many functions also send data *back* to the main program. We say
these functions **return** a value.

Return Statements
-----------------

.. index::
   single: return; value

One example of a function that returns a value is ``len()``. When called, the
function takes an argument---like a string or a list---and figures out how many
characters or elements are in the collection. We do not need to know HOW the
``len()`` function works. We just need the result.

``len()`` *returns* the answer we want---the length of the collection. We send
the function an argument (a string or list), and it sends back an integer in
response.

The returned result is the output of the function, and we can picture the
process something like this:

.. figure:: figures/return-diagram.png
   :alt: Diagram that shows sending an argument ('Python') to the len() function and returning the value 6.

   The argument 'Python' is sent to the len() function, and the function returns
   the value 6.

We can see this result if we ``print(len('Python'))``:

::

   6

Note that we do NOT see ``"len('Python')"`` or ``Python`` on the screen.
Instead, the code prints the value *returned* by the ``len()`` function.

Returning a Value
^^^^^^^^^^^^^^^^^

To return a value from functions that we create, we add a **return statement**
to the function body. A return statement has the general syntax:

.. sourcecode:: python

   return some_value

``return`` is the keyword that tells Python: "Send information back to the main
program." ``some_value`` is the data that gets returned, and it may be any data
type (``float``, ``str``, ``bool``, ``list``, etc.).

Functions can return the value of a variable or the result of an expression.
For example, ``return num`` returns whatever value has been assigned to
``num``, while ``return num >= 20`` sends back either ``True`` or ``False``.

.. admonition:: Example

   This function has a single parameter, ``an_int``, which is expected to be
   a positive integer. It returns the sum of ``1 + 2 + ... + an_int``.

   .. sourcecode:: python
      :linenos:

      def sum_one_to_n(an_int):
         total = 0
         for number in range(1, an_int+1):
            total += number

         return total

      result = sum_one_to_n(3)
      print(result)

   **Console Output**

   ::

      6

   Notice that the function ``sum_one_to_n`` contains no ``print`` statements!

Let's take a look at the order of events after we call the function:

#. ``sum_one_to_n(3)`` calls the function and sends it the argument ``3``.
#. Python assigns the argument to the parameter (``an_int = 3``) and then
   runs the function body. ``total`` stores the result from the accumulator
   pattern.
#. Line 6 *returns* the value of ``total`` back to the main program.
#. Line 8 assigns the answer returned by the function to the variable
   ``result``.
#. The output we see comes from the final line of the program, which prints the
   value of ``result``.

.. admonition:: Note

   A ``return`` statement does not print anything. If we want to see the value
   returned by a function, then we must print it AFTER calling the function.

.. _draw-square-code:

No ``return`` Value
^^^^^^^^^^^^^^^^^^^

Not every function needs to return a value. For example, we can define the
``draw_square`` function for a turtle as follows:

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      import turtle

      def draw_square(turtle_name, side_length):
         for side in range(4):
            turtle_name.forward(side_length)
            turtle_name.left(90)
      
      bob = turtle.Turtle()
      draw_square(bob, 100)

When we call ``draw_square`` in line 9, we do not want the function to give us
an *answer*. Instead, we want it to make a turtle draw a specific shape on the
screen. In this case, the function does not need to send any data back to the
main program. Once the turtle finishes moving, the function ends, and control
passes to the statement after the function call.

When we write a function, we must decide whether or not it will return data
once its job is done. We do not need to include the ``return`` keyword in
every function.

``return`` Stops a Function
---------------------------

When a ``return`` statement executes, the function ends, even if more code
follows in the function body. We must be careful to use ``return`` only when
the work of the function is done.

.. admonition:: Example

   The ``print`` statements in this function never execute, since the function
   returns before either one is reached.

   .. sourcecode:: python
      :linenos:

      def past_the_point_of_return():
         return "I'm done!"
         print("This will NOT be printed!!!!!")
         for line in range(100):
            print("Neither will this!!!!!")

      message = past_the_point_of_return()
      print(message)

   **Console Output**

   ::

      I'm done!

   Written this way, the function behaves as if lines 3 - 5 do not exist!

We can use the fact that ``return`` ends a function to force it to stop at a
specific point.

.. admonition:: Try It!

   This function adds up the integers ``0...n``. However, if we send in an argument
   that is not a positive integer, the function sends back an error message.

   .. raw:: html

      <iframe src="https://trinket.io/embed/python/14412b9424?runOption=run" width="100%" height="350" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

   On line 12, try replacing the argument in the function call with:

   #. a negative number,
   #. a decimal value,
   #. a string (like ``'abc'``).

Consider what happens if we call the ``sum_one_to_n()`` function and use the
string ``'abc'`` as the argument. Since the ``if`` statement in line 3 (``type('abc') != int``)
is ``True``, the ``return`` statement on line 4 runs and sends the error message back to the main program.
In this case, the ``for`` loop on line 7 does not run.

Try It!
-------

#. In the editor below, define a function called ``double_value``, which takes
   a single parameter called ``value``.
#. Inside the function, add the statement ``return value*2``. Don't forget to
   indent!
#. Run your program to check for error messages. If any occur, fix the bugs and
   try again. Properly done, NOTHING shows up in the console! The code contains
   no ``print`` statements yet.
#. Below the function, define a new variable and assign it to ``double_value(4)``.
#. Finally, print the value of your new variable.
#. Run your program to check your work. For ``double_value(4)``, the printed
   result should be ``8``.

   .. raw:: html

      <iframe src="https://trinket.io/embed/python/c96a6ba9a4?runOption=run" width="100%" height="300" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

#. What happens if you send in a string instead of a number?
#. Assign a value to a variable, then call the function with the variable as
   the argument (e.g. ``double_value(variable_name)``).

Check Your Understanding
------------------------

.. admonition:: Question

   What does the following code output?

   .. sourcecode:: python
      :linenos:

      def plus_two(a_number):
         return a_number + 2

      total = 2

      for turn in range(4):
         total = plus_two(total)

      print(total)

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> 4</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> 6</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> 8</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, true)"> 10</li>
      </ol>
      <p id="Q1"></p>

.. Answer = d

.. admonition:: Question

   What does the following function *return*?

   .. sourcecode:: python
      :linenos:

      def say_hello(user_input = 'World'):
         if type(user_input) != str:
            return "Invalid entry."
            
         return "Hello, {0}!".format(user_input)
      
      message = say_hello(5)

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">Hello, World!</span></li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">Hello, 5!</span></li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, true)"> <span style="color:#419f6a; font-weight: bold">Invalid entry.</span></li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> Nothing is returned by the function</li>
      </ol>
      <p id="Q2"></p>

.. Answer = c

.. admonition:: Question

   Three of the following functions should include a ``return`` statement,
   while the others do not need one. Pick the functions that *require* a
   ``return``.

   .. raw:: html
      
      <ol type="a">
         <li><span id = "A1" onclick="highlight('A1', true)">calculate_area</span></li>
         <li><span id = "B1" onclick="highlight('B1', false)">draw_polygon</span></li>
         <li><span id = "C1" onclick="highlight('C1', false)">print_names</span></li>
         <li><span id = "D1" onclick="highlight('D1', true)">find_average_score</span></li>
         <li><span id = "E1" onclick="highlight('E1', false)">change_screen_color</span></li>
         <li><span id = "F1" onclick="highlight('F1', true)">create_sorted_string</span></li>
      </ol>

.. Answers = a, d, f

