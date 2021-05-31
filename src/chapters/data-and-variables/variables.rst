Variables
=========

.. index:: ! variable

One of the most powerful features of a programming language is the ability to manipulate variables.
A **variable** is a name that refers to a value.
Recall that a value is a single, specific piece of data, such as a specific number or string.
Variables allow us to store values for later use.

A useful visual analogy for how a variable works is that of a label that *points to* a piece of data. 

.. figure:: figures/variable.png
   :alt: A label, programmingLanguages, pointing to a the string value "JavaScript"

   A variable can be visualized as a label pointing to a specific piece of data.

In this figure, the name ``programmingLanguage`` points to the string value ``"JavaScript"``. 
This is more than an analogy, since it also is representative of how a variable and its value are stored in a computer's memory.

With this analogy in mind, let's look at how we can formally create variables in Python.

Assigning Values
----------------

.. index:: ! assignment statement

**Assignment statements** create new variables and also give them values to
refer to. The syntax for an assignment statement is:

.. sourcecode:: Python

   variable_name = value

The assignment statement links a name, on the left hand side of the ``=``, with
the value on the right hand side. The *value* refers to any type of data.

.. admonition:: Example

   .. sourcecode:: Python

      message = "Python ROCKS!"
      num = 17
      pi = 3.14159

This example makes three assignments. The first assigns the string value
``"Python ROCKS!"`` to a new variable named ``message``. The second gives the
integer ``17`` to ``num``, and the third assigns the float ``3.14159`` to a
variable called ``pi``.

.. admonition:: Warning

   The ``=`` sign does NOT work both ways. ``17 = num`` causes an error. The
   variable name MUST be on the left, and the value MUST be on the right.

One common mistake is to confuse the assignment operator ``=`` with the idea of
equality (things being the same). *Equality* compares two values, like ``5``
vs. ``4`` or ``'dog'`` vs. ``'dog'``. *Assignment* gives a value to a variable.

We will explore *equality* later and see that it uses the ``==`` operator
instead of ``=``.

Evaluating Variables
--------------------

.. index:: variable, evaluation

Once we create a variable and assign it a value, we can use the variable name to refer to that value.

.. admonition:: Example

   These two examples give the exact same output.

   .. sourcecode:: python

      print("Hello, World!")

   .. sourcecode:: python
      :linenos:

      message = "Hello, World!"
      print(message)

In the second example just above, the variable name ``message`` points to the 
value ``"Hello, World"``. ``print(message)`` means the same thing as ``print("Hello, World!")``, so we
say that ``message`` **evaluates to** ``"Hello, World!"``

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      message = "Python ROCKS!"
      num = 17
      pi = 3.14159

      print(message)
      print(num)
      print(pi)

   **Console Output**

   ::

      Python ROCKS!
      17
      3.14159

In each case, the printed result is the value of the variable. 

Like values, variables also have types. We determine the type of a variable the same way we determine the type of a value, using ``type()``.

.. admonition:: Example

   .. sourcecode:: py
      :linenos:
      
      message = "What's up, Doc?"
      n = 17
      pi = 3.14159

      print(type(message))
      print(type(n))
      print(type(pi))

   **Console Output**

   ::

      <class 'str'>
      <class 'int'>
      <class 'float'>

The type of a variable is the type of the data it currently refers to.

Reassigning Variables
---------------------

We use variables in a program to store values, like the current score at
a football game. Just like a score, variables can change over time.

To see this, read and then run the following program. Notice how we change the
value of ``day`` three times. We even give it a value of a different data type.

.. sourcecode:: py
   :linenos:

   day = "Thursday"
   print(day)

   day = "Friday"
   print(day)

   day = 21
   print(day)

A great deal of programming involves asking the computer to remember things.
For example, we might want to keep track of the number of missed calls on our
phones. Each time we miss another call, we can update a variable to reflect the
new total.

Check Your Understanding
------------------------

.. admonition:: Question

   What is printed when the following code executes?

   .. sourcecode:: py
      :linenos:

       day = "Thursday"
       day = 32.5
       day = 19
       print(day)

   a. Nothing is printed. A runtime error occurs.
   b. ``Thursday``
   c. ``32.5``
   d. ``19``

.. admonition:: Question

   How can you determine the type of a variable?

   a. Print out the value and determine the data type based on the value printed.
   b. Use ``type()``.
   c. Use it in a known equation and print the result.
   d. Look at the declaration of the variable. 


