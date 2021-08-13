Function Output
===============

The final part of the function machine is the function providing output.
Let's take a look at function output in greater detail.

Return Statements
-----------------

.. index::
   single: return
   single: return; value

Some functions return values that are useful. In particular, the type conversion functions convert input to the specified data type and return the result---calling ``Number("3.14")`` returns the value ``3.14``.

Returning a Value
^^^^^^^^^^^^^^^^^

To return a value from functions that *we* create, we can use a **return statement**. A return statement has the form:

.. sourcecode:: py

   return someVal

where ``someVal`` is any value.

.. admonition:: Example

   This function has a single parameter, ``n``, which is expected to be a
   positive integer. It returns the sum 1+2+...+n.

   .. sourcecode:: py
      :linenos:

      def sum_to_n(n):
         sum = 0
         for i in range(n+1):
            sum += i
         return sum

      print(sum_to_n(3))

   **Console Output**

   ::

      6

Notice that ``sum_to_n`` does not print anything; the output comes from the final
line of the program, which prints the value *returned by* the function call
``sum_to_n(3)``.

Now that we have return statements in our coding toolbox, we will very rarely
print anything *within* a function. If we want to see the value returned by a
function then we must print it *after* calling the function.

.. admonition:: Question

   The function ``sum_to_n`` uses a pattern that we have seen previously. What is
   it called?

``return`` Terminates Function Execution
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

When a return statement executes, the function terminates, regardless of whether or not there is any code following the return statement. This means that you must be careful to use ``return`` only when the work of the function has been completed.

.. admonition:: Example

   This ``print()`` statement in this function never executes, since the function returns before it is reached.

   .. sourcecode:: py
      :linenos:

      def pastThePointOfReturn():
         return "I'm done!"
         print("This will not be printed")

      print(pastThePointOfReturn())

   **Console Output**

   ::

      I'm done!

We can use the fact that ``return`` stops the execution of a function intentionally, to force a function to stop execution.

.. admonition:: Example

   This function prints out the integers 1...n using an infinite ``while`` loop, which nonetheless terminates when the ``return`` statement is executed.

   .. sourcecode:: py
      :linenos:

      def count_to_n(n):
         count = 1
         while True:
            if count > n:
               return
            print(count)
            count += count

Boolean Functions
^^^^^^^^^^^^^^^^^

.. index::
   pair: function; boolean

A function that returns a boolean value is known as a **boolean function**. Perhaps the simplest such function is one that tests an integer to determine if it is even.

.. admonition:: Example

   .. sourcecode:: py
      :linenos:

      def is_even(n):
         if n % 2 == 0:
            return True
         else:
            return False

      print(is_even(4))
      print(is_even(7))

   **Console Output**

   ::

      True
      False

It is conventional to name boolean functions by starting with either ``is`` or ``has``, which creates a nice semantic effect when reading the code.
For example, reading ``is_even(4)`` communicates to the reader that the function should answer the question, "Is 4 even?" This is a convention so widely used by programmers that it extends to nearly every language. 

Let's return to the ``is_even`` function above, to see how we can use the power of return statements to make it even better.

Since ``return`` terminates the function, we can leave out the ``else`` clause and have the same effect. This is because if ``n`` is even, the return statement in the ``if`` block will execute and the function will end. If ``n`` is odd, the ``if`` block will be skipped and the second return statement will execute.

.. sourcecode:: py
   :linenos:

   def is_even(n):
      if n % 2 == 0:
         return True
      return False

This updated version works exactly the same as our initial function. 

Additionally, notice that the function returns ``True`` when ``n % 2 == 0`` returns ``True``, and it returns ``False`` when ``n % 2 == 0`` returns ``False``.
In other words, the return value is *exactly the same* as the value of ``n % 2 == 0``. This means that we can simplify the function even further by returning the value of this expression.

.. sourcecode:: py
   :linenos:

   def is_even(n):
      return n % 2 == 0

This version of ``is_even`` is better than the first two, not because it is shorter (shorter isn't always better), but because it is simpler to read. We don't have to break down the conditional logic to see what is being returned.

Most boolean functions can be written so that they return the value of a boolean expression, rather than explicitly returning ``True`` or ``False``. 

Parameters and Arguments
-------------------------

.. index::
   single: function; argument
   single: function; parameter

Over the past few sections, we introduced two function-related concepts that are very similar, and are often confusing to distinguish: *arguments* and *parameters*. The difference between the two is subtle, so we will attempt to clear that up now.

The easiest way to talk about the difference between arguments and parameters is by referring to an example.

.. admonition:: Example

   The function ``hello`` takes a single value, which we expect to be a person's name, and returns a message that greets that person. 

   ..TODO: this is getting parsed as python when 'py' is specified. whats going on here?

   .. sourcecode:: js
      :linenos:

      def hello(name):
         return `Hello, ${name}!`

      print(hello("Lamar"))

   **Output**

   ::

      Hello, Lamar!


In this example, ``name`` is a **parameter**. It is part of the function definition, and *behaves like a variable* that exists only within the function.

The value ``"Lamar"`` that is used when we invoke the function on line 5 is an **argument**. It is a *specific value* that is used during the function call. 

The difference between a parameter and an argument is the same as that between a variable and a value. A variable *refers to* a specific value, just like a parameter *refers to* a specific argument when a function is called. Like a value, an argument is a concrete piece of data.

Arguments Are Optional
----------------------

A function may be defined with several parameters, or with no parameters at all. Even if a function is defined with parameters, Python will not complain if the function is called *without* specifying the value of each parameter.

.. admonition:: Example

   .. TODO: not parsed as python using 'py'. I think the string substitution syntax needs to be python-iified

   .. sourcecode:: js
      :linenos:

      def hello(name):
         return `Hello, ${name}!`

      print(hello())

   **Output**

   ::

      Hello, undefined!

We defined ``hello`` to have one parameter, ``name``. When calling it, however, we did not provide any arguments. Regardless, the program ran without error.

*Arguments are optional* when calling a function. When a function is called
without specifying a full set of arguments, any parameters that are left
without values will have the value ``undefined``.

.. index::
   single: function; default parameter

If your function will not work properly without one or more of its parameters defined, then you should define a **default value** for these parameters. The default value can be provided next to the parameter name, after ``=``.

.. admonition:: Example

   This example modifies the ``hello`` function to use a default value for ``name``. If ``name`` is not defined when ``hello`` is called, it will use the default value.

   .. TODO: not parsed as python using 'py'. I think the string substitution syntax needs to be python-iified
   
   .. sourcecode:: javascript
      :linenos:

      def hello(name = "World"):
         return `Hello, ${name}!`

      print(hello())
      print(hello("Lamar"))

   **Console Output**

   ::

      Hello, World!
      Hello, Lamar!

Check Your Understanding
------------------------

.. admonition:: Question

   What does the following code output?

   .. sourcecode:: py
      :linenos:

      def plus_two(num):
         return num + 2

      a = 2

      for i in range(4):
         a = plus_two(a)

      print(a)

.. admonition:: Question

   What does the following function *return*?

   .. sourcecode:: py
      :linenos:

      def repeater(str):
         repeated = str + str
         print(repeated)

      repeater('Bob')

   #. ``"BobBob"``
   #. Nothing (no return value)
   #. ``undefined``
   #. The value of ``Bob``

.. admonition:: Question

   What does the following code *output*?

   .. sourcecode:: py
      :linenos:

      def repeater(str):
         repeated = str + str
         print(repeated)

      repeater('Bob')

   #. ``"BobBob"``
   #. Nothing (no output)
   #. ``undefined``
   #. The value of ``Bob``
