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

Declaring and Initializing Variables
------------------------------------

.. index:: 
   pair: variable; declaration

.. index:: ! declaration

.. index:: 
   pair: variable; assignment
   pair: variable; initialization

.. index:: ! assignment, ! initialization

To create a variable in Python, create a new name for the variable and give it a value:

.. sourcecode:: python
    
    programmingLanguage = "JavaScript"

This creates a variable named ``programmingLanguage``. The act of creating a variable is referred to as **variable declaration**, or simply **declaration**.
Once a variable has been declared, it may be given a value using an **assignment statement**, which uses ``=`` to give a variable a value.

The act of assigning a variable a value for the first time is called **initialization**.

In other languages, declaration and initialization are separated across multiple lines, however, Python does this all in one line.

To give a variable a value, use the **assignment operator**, ``=``.
This operator should not be confused with the concept of *equality*, which expresses whether two things are the "same" (we will see later that equality uses the ``===`` operator). 
The assignment statement links a *name*, on the left-hand side of the operator, with a *value*, on the right-hand side. This is why you will get an error if you try to run:

.. sourcecode:: python

    "JavaScript" = programmingLanguage

An assignment statement must have the name on the left-hand side, and the value on the right-hand side.

.. admonition:: Tip

   To avoid confusion when reading or writing code, say to yourself:

   ``programmingLanguage`` is assigned ``'JavaScript'``

   or

   ``programmingLanguage`` gets the value ``'JavaScript'``.

   Don't say: 
   
   ``programmingLanguage`` equals ``'JavaScript'``.

Evaluating Variables
--------------------

.. index:: variable; evaluation

After a variable has been created, it may be used later in a program anywhere a value may be used. For example, ``print()`` prints a value, we can also give ``print()`` a variable.

.. admonition:: Example

   These two examples have the exact same output.

   .. sourcecode:: python

      print("Hello, World!")

   .. sourcecode:: python
      :linenos:

      message = "Hello, World!"
      print(message)

When we refer to a variable name, we are **evaluating** the variable.
The effect is just as if the value of the variable is substituted for the variable name in the code when executed.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      message = "What's up, Doc?"
      n = 17
      pi = 3.14159

      print(message)
      print(n)
      print(pi)

   **Console Output**

   ::

      What's up, Doc?
      17
      3.14159

In each case, the printed result is the value of the variable. 

Like values, variables also have types.
We determine the type of a variable the same way we determine the type of a value, using ``type()``.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:
      
      message = "What's up, Doc?"
      n = 17
      pi = 3.14159

      print(type(message))
      print(type(n))
      print(type(pi))

   **Console Output**

   ::

      string
      number
      number

The type of a variable is the type of the data it currently refers to.

Reassigning Variables
---------------------

We use variables in a program to "remember" things, like the current score at the baseball game.
As their name implies, variables can change over time, just like the scoreboard at a baseball game.
You can assign a value to a variable, and later assign it a different value.

To see this, read and then run the following program in a code editor.
You'll notice that we change the value of ``day`` three times, and on the third assignment we even give it a value that is of a different data type.

.. sourcecode:: python
   :linenos:

    day = "Thursday"
    print(day)

    day = "Friday"
    print(day)

    day = 21
    print(day)

A great deal of programming involves asking the computer to remember things.
For example, we might want to keep track of the number of missed calls on your phone.
Each time another call is missed, we can arrange to update a variable so that it will always reflect the correct total of missed calls.

Check Your Understanding
------------------------

.. admonition:: Question

   What is printed when the following code executes?

   .. sourcecode:: python
      :linenos:

       day = "Thursday"
       day = 32.5
       day = 19
       print(day)

   1. Nothing is printed. A runtime error occurs.
   2. ``Thursday``
   3. ``32.5``
   4. ``19``

    
.. admonition:: Question

   How can you determine the type of a variable?

   1. Print out the value and determine the data type based on the value printed.
   2. Use ``type()``.
   3. Use it in a known equation and print the result.
   4. Look at the declaration of the variable. 
