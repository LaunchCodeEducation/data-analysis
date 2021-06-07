Defining Our Own Functions
==========================

Built-in functions in Python give us a lot of capabilities. Indeed, we gain even more coding potential by 
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

      def add_list_numbers(list_name):
         total = 0
         for number in list_name:
            total += number
         
         return total

      print("Hello, World!")

   Line 1 defines the function name and parameter. Lines 2 - 6 are part of the
   function body. Line 8 is even with the ``def`` keyword, so it is NOT part of
   the ``add_list_numbers`` function.
            
Try It!
-------

Let's see function syntax in action. We first consider a loop that prints a
list of names.

.. sourcecode:: Python
   :linenos:

   names = ["Lena", "James", "Julio"]
   other_names = ["Devon", "Colin", "Nalini Nadkarni"]

   for name in names:
      print(name)

As written, this loop only prints out the names from the first list. Let's
create a function that prints out the items from *any* list of names.

.. admonition:: Example

   Follow these steps to code your first function:

   #. On line 2, use the ``def`` keyword to set the name of the function and
      the name of the parameter. Don't forget to end the line with a colon.

      ``def print_names(names_list):``

   #. On lines 3 and 4, use a ``for`` loop to print each name from
      ``names_list``. Don't forget to indent the lines compared to the ``def``
      statement!

      .. sourcecode:: Python
         :lineno-start: 3
      
         for name in names_list:
            print(name)

   #. Click *Run* to make sure your code contains no syntax errors. If it
      does, debug the code before moving on.
   #. The program will not actually print anything to the console yet, but we
      will fix that in a moment!

   .. raw:: html

      <iframe height="500px" width="100%" src="https://repl.it/@launchcode/Print-Names-Function?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

We can now use ``print_names`` just like the built-in Python functions. To
*call* our function, we need to type its name and include a list as the
argument.

In the editor above, call our new function twice by adding these
lines below the function body:

.. sourcecode:: Python

   print_names(names)
   print('------')
   print_names(other_names)

Run the code and examine the output. By calling the function with different
arguments (``names`` and ``other_names``), we use the same loop to print the
elements of each list to the console.

.. admonition:: Note

   There is nothing about our function that forces ``names_list`` to actually
   contain names, or even strings. The function will work the same for ANY
   list it is given. (TRY IT!) 
   
   Therefore, a better name for this function would be ``print_list_items``!

Defining vs. Calling
--------------------

When we *define* a function, we make it available for later use. However, a
function does NOT run when it is defined. It must be *called* in order to
execute.

.. admonition:: Warning

   This is not only a common point of confusion for new programmers, but it can
   also cause logic errors!

Let's look at another example to see how this works.

.. admonition:: Try It!

   What happens if we define a function without calling it?

   Run the following code as-is (the code contains no bugs). What gets printed? 

   .. raw:: html

      <iframe height="400px" width="100%" src="https://repl.it/@launchcode/Say-Hello-Function?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

   #. In order for a function to run, it must be *called* by using its name.
      Add the code ``say_hello()`` in line 5 and run the program again.
   #. Does it matter if the ``say_hello()`` statement is indented relative to
      the ``def`` statement?  Try changing the indentation to check!
   #. Does it matter if we include parentheses in line 5? Try using
      ``say_hello`` instead of ``say_hello()``. 

Check Your Understanding
------------------------

.. admonition:: Question

   What are the *parameters* of the following function? Click *ALL* that apply.

   .. sourcecode:: Python
      :linenos:

      def draw_square(turtle_name, side_length):
         for side in range(4):
            turtle_name.forward(side_length)
            turtle_name.left(90)
      
      bob = turtle.Turtle()
      draw_square(bob, 100)

   .. raw:: html
      
      <ol type="a">
         <li><span id = "A1" onclick="highlight('A1', false)">bob</span></li>
         <li><span id = "B1" onclick="highlight('B1', true)">turtle_name</span></li>
         <li><span id = "C1" onclick="highlight('C1', true)">side_length</span></li>
         <li><span id = "D1" onclick="highlight('D1', false)">side</span></li>
         <li><span id = "E1" onclick="highlight('E1', false)">100</span></li>
      </ol>

.. Answers = b & c

.. admonition:: Question

   For the same code sample, what are the *arguments* sent by the function call?
   Click *ALL* that apply.

   .. raw:: html
      
      <ol type="a">
         <li><span id = "A2" onclick="highlight('A2', true)">bob</span></li>
         <li><span id = "B2" onclick="highlight('B2', false)">turtle_name</span></li>
         <li><span id = "C2" onclick="highlight('C2', false)">side_length</span></li>
         <li><span id = "D2" onclick="highlight('D2', false)">side</span></li>
         <li><span id = "E2" onclick="highlight('E2', true)">100</span></li>
      </ol>

.. Answers = a & e

.. admonition:: Question

   True or False: A function can be run several times by placing the function
   call inside a loop. 

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, true)"> True</li>
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, false)"> False</li>
      </ol>
      <p id="Q3"></p>

.. Answer = a

.. admonition:: Question

   Which is the BEST name for the following function?

   .. sourcecode:: python
      :linenos:

      def func_name(radius):
        area = 3.14159 * radius**2
        return area

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q4" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">area</span></li>
         <li><input type="radio" name="Q4" autocomplete="off" onclick="evaluateMC(name, true)"> <span style="color:#419f6a; font-weight: bold">calculate_area_of_circle</span></li>
         <li><input type="radio" name="Q4" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">circle</span></li>
         <li><input type="radio" name="Q4" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">shape</span></li>
      </ol>
      <p id="Q4"></p>

.. Answer = b

