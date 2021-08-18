Parameters and Variables
========================

Earlier, we said that a parameter "behaves like a variable within the
function." While this is true, the relationship between variables and
parameters is a bit more complicated.

.. _function-scope:

Function Scope
--------------

.. index:: ! scope

.. index::
   single: function; scope

The **scope** of a variable refers to where that variable is useable within a
program. Scope consists of all locations in a program where a variable can be
used or modified.

.. admonition:: Warning

   A variable defined inside a function is NOT usable outside of that
   function.

Consider the following function, which takes a string as a parameter and
returns a new string without hyphens, ``-``.

.. admonition:: Try It!

   #. Run the program as-is, and examine the output.
   #. On line 3, add the following code to the function body. Re-run the
      program and examine the output.

      .. sourcecode:: python
         :lineno-start: 3

            print(phone_number, str_with_hyphens)

   #. On line 9, add ``print(without_hyphens)`` and run the program one more
      time. You should receive an error message.

   .. replit:: py
      :slug: FunctionScope
      :linenos:

      def remove_hyphens(str_with_hyphens):
         without_hyphens = str_with_hyphens.replace('-', '')

         return without_hyphens

      phone_number = "555-555-5555"
      no_hyph_number = remove_hyphens(phone_number)
      print(no_hyph_number)

In *step 1*, the function ``remove_hyphens`` behaves as expected. It takes the
argument ``"555-555-5555"``, removes the ``"-"`` symbols, and returns the
result. Line 7 assigns that result to the variable ``no_hyph_number``, and line
8 prints it to the console.

In *step 2*, the ``print`` statement on line 3 shows us that the value of
``phone_number`` has been assigned to the parameter ``str_with_hyphens``. Both
variables are *visible* inside the function.

.. admonition:: Warning

   Since the original variable and the parameter have the same values, you
   might be tempted to just use ``phone_number`` in the function.

      DON'T!

   We will explain why later, but it is important that you recognize this
   warning now.

In *step 3*, we receive an error message (``NameError: name 'without_hyphens' is
not defined``) when we try to print ``without_hyphens`` on line 9.

Line 7 calls ``remove_hyphens``, which returns ``without_hyphens`` with the
value ``"5555555555"``. However, once the function finishes *ALL VARIABLES AND
PARAMETERS WITHIN THE FUNCTION ARE DESTROYED*.

This is why line 9 produces a ``NameError``---there is no longer a variable
named ``without_hyphens``.

This is what we mean when we refer to **scope**. A variable is not always
usable throughout an entire program. Where it can be used depends on where it
is defined.

   Parameters and variables defined inside a function are only visible within
   that function.

Variable Shadowing
------------------

What about variables defined OUTSIDE of a function? We saw above that
``phone_number`` was visible inside of the ``remove_hyphens`` function.

This situation is more complicated. A variable defined outside a
function *may* be visible within the function, but using it or trying to
change its value creates problems.    

.. admonition:: Try It!

   Let's take another look at our ``remove_hyphens`` function.

   #. Run the program as-is, and examine the output.
   #. On line 3, add the following code to the function body. Re-run the
      program and examine the output.

      .. sourcecode:: python
         :lineno-start: 3

            phone_number = '1234'

   .. replit:: py
      :slug: ScopeExample02
      :linenos: 

      def remove_hyphens(str_with_hyphens):
         without_hyphens = str_with_hyphens.replace('-', '')

         print(phone_number)
         return without_hyphens

      phone_number = "555-555-5555"
      no_hyph_number = remove_hyphens(phone_number)
      print(no_hyph_number)
      print(phone_number)

In *step 1*, even though ``phone_number`` is defined outside the function, it is
still visible within the function. When ``remove_hyphens`` is called and
``print(phone_number)`` on line 4 runs, ``phone_number`` has the value
``"555-555-5555"``. This means that the scope of ``phone_number`` extends into
the function ``remove_hyphens``.

In *step 2*, we assign ``phone_number`` a value of ``'1234'`` in line 3. Now line
4 displays that new number in the console. However, line 10 still prints the
*original* value ``555-555-5555``.

Line 3 actually defines a NEW ``phone_number`` variable inside the function,
and this variable is *different* from the one outside of the function. This
situation confuses many new coders---we created two variables that have the
same name but different values. Yuck!

.. admonition:: Tip

   Do NOT define variables inside a function that use the same names found
   outside of the function.

.. admonition:: Example

   What if we did something like this:

   .. sourcecode:: python
      :linenos:
   
      def remove_hyphens(phone_number):
         without_hyphens = phone_number.replace('-', '')
         return without_hyphens

      phone_number = "614-555-5555"
      no_hyph_number = remove_hyphens('56-78')

   We don't recommend doing this! Are you having trouble interpreting this code?
   When the function runs, does ``phone_number`` on line 2 have the value ``"614-555-5555"`` or
   ``'56-78'``? Feel free to run this code in the editor above to find out.

.. index::
   single: variable; shadowing

An interesting thing happens when a function parameter has the same name as a
variable defined outside of that function.

While the variable ``phone_number`` declared on line 5 is visible inside
``remove_hyphens``, it is *hidden* by the function parameter with the same
name. When ``remove_hyphens('56-78')`` is called, and
``phone_number.replace('-', '')`` runs, ``phone_number`` has the value
``'56-78'``, which is the argument passed into the function.

This situation is called **shadowing**. We can imagine that a function
parameter *casts a shadow* over a variable of the same name and hides it from
view.

.. admonition:: Warning

   There is NO good reason to allow variable shadowing in your programs! 
   
   *Avoid giving variables and function parameters the same name.*

Check Your Understanding
------------------------

.. admonition:: Question

   What does the following code output?

   .. sourcecode:: python
      :linenos:

      def is_even(num): 
         return num % 2 == 0

      num = 42
      print(is_even(43))

   a. True
   b. False

.. Answer = b


