.. _input:

Input with ``input()``
======================

``print()`` works fine for printing static (unchanging) messages to the
screen. If we wanted to print a phrase greeting a specific user, then
``print("Hello, Dave.")`` would be OK as long as Dave is the actual
user.

What if we want to greet someone else? We could change the string inside the
``()`` to be ``'Hello, Sarah'`` or ``'Hello, Elastigirl'`` or any other name we
need. However, this is inefficient. Also, what if we do not know the name of
the user beforehand? We need to make our code more general and able to respond
to different conditions.

It would be great if we could ask the user to enter a name, store that string
in a variable, and then print a personalized greeting using ``print()``.
Variables to the rescue!

Requesting Data
---------------

.. index:: ! input

.. index:: ! prompt

To personalize the greeting, we have to get **input** from the user. This
involves displaying a **prompt** on the screen (e.g. "Please enter a number:
"), and then waiting for the user to respond. Whatever information the user
enters gets stored for later use.

As we saw earlier, each programming language has its own way of accomplishing
the same task. The Python syntax is ``input("Please enter your
name: ")``.

If we want to get user input to print a customized greeting, we can do the following:

.. sourcecode:: py
   :linenos:

   user = input("Please enter your name: ")
   print("Hello " + user + "!")

Critical Input Detail
----------------------

There is one very important quirk about the input function that we need to
remember. Given ``print(7 + 2)``, the output would be ``9``.

Now explore the following code, which prompts the user for two numbers and then
prints their sum:

.. replit:: py
   :slug: InputExamples02Py
   :linenos:

   num1 = input("Enter a number: ")
   num2 = input("Enter another number: ")

   print(num1 + num2)

Run the program, enter your choice of numbers, and examine the output. Do you
see what you expected?

If we enter ``7`` and ``2``, we expect an output of ``9``.  We do NOT expect
``72``, but that is the result printed. What gives?!?!?

The quirk with the ``input`` function is that it *treats all entries as
strings*, so numbers get concatenated rather than added.  Just like
"Hello, " + "World" outputs as ``Hello, World``, "7" + "2" outputs as ``72``.

   Python treats input entries as strings!

If we want our program to perform math on the entered numbers, we must
:ref:`use type conversion <type-conversion>` to change the string values into
numbers.

.. admonition:: Try It

   #. Use ``int()`` to convert ``num1`` and ``num2`` from strings to numbers.
      Run the program and examine the result.
   #. Instead of using two steps to assign ``num1`` and then convert it, combine
      the steps in line 3. Place ``input("Enter a number: ")`` inside
      the ``int()`` function. Run the program and examine the result.
   #. Repeat step 2 for ``num2``
   #. What happens if a user enters ``Hi`` instead of a number?

Check Your Understanding
------------------------

.. admonition:: Question

   What is printed when the following program runs?

   .. sourcecode:: py
      :linenos:

      info = input("Please enter your age: ")
      # The user enters 25.

      print(type(info))

   a. ``string``
   b. ``number``
   c. ``info``
   d. ``25``
