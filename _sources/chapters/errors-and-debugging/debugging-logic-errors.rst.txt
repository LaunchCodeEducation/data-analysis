.. _fixing-logic-errors:

Fixing Logic Errors
===================

We debug syntax and runtime mistakes by looking at syntax highlighting and
reading any error messages produced. Unfortunately, logic errors do not
generate error messages or show up in the code highlighting. This makes them
tougher to debug.

If there is a logic error in our program, it will run without crashing.
However, it will NOT do the right thing. Remember that programs do *exactly*
what we tell them to. If we include a logic error in our code, then the program
will do *exactly* the wrong thing.

While we can't provide a step-by-step approach that works for every possible
logic error, we *can* start with one basic and effective strategy.

Printing Values
---------------

When our code runs but doesn't give the expected results, it is important to
check the values of the variables as they get used. We must also feed the
program a specific set of data, and then compare the output to a known, correct
answer.

Let's look at a program that has a logical bug.

.. sourcecode:: python
   :linenos:

   hours = input('Enter a number of hours: ')
   minutes = hours * 60

   print('Number of minutes = ', minutes)

This program asks the user for a number of hours and tries to convert it into
the matching number of minutes. Since there are 60 minutes in 1 hour, entering
``2`` for the hours should show us a result of ``120`` minutes. However,
running the program as-is and entering ``2`` gives the output:

::

   Enter a number of hours: 2
   Number of minutes =  222222222222222222222222222222222222222222222222222222222222

This is clearly incorrect. The program runs without an error message, so the
only way we see the mistake is to know that the answer should be ``120``.

.. admonition:: Tip

   After fixing syntax and runtime errors, ALWAYS test your code by using a
   set of data that should produce an answer you ALREADY know.

Without an error message, it is not immediately clear what went wrong. To
figure it out, we'll use ``print`` to check the values of key variables as the
program runs. 

Let's first make sure that ``hours`` looks like it should by adding a ``print``
statement just after we create the variable.

.. sourcecode:: python
   :linenos:

   hours = input('Enter a number of hours: ')
   print(hours)
   minutes = hours * 60

   print('Number of minutes = ', minutes)

Running this with an input of ``2`` gives the output:

::

   Enter a number of hours: 2
   2
   Number of minutes =  222222222222222222222222222222222222222222222222222222222222

The second line is the value of ``hours``, which appears to be correct.
Unfortunately, the final answer is still wrong, so we need to keep digging for
more information.

Looking at the line where we assigned ``minutes``, we see that we want to
multiply ``hours`` by 60. We assume that ``hours`` is a numerical value.

Let's check the data type for ``hours``.

.. sourcecode:: python
   :linenos:

   hours = input('Enter a number of hours: ')
   print(hours, type(hours))
   minutes = hours * 60

   print('Number of minutes = ', minutes)

Running this with an input of ``2`` gives the output:

::

   Enter a number of hours: 2
   2 <class 'str'>
   Number of minutes =  222222222222222222222222222222222222222222222222222222222222

That's it! The variable ``hours`` has the value ``2``, but it is a *string*
rather than a number. When we assigned ``minutes`` the formula ``hours * 60``,
we told Python to repeat the string 60 times: ``"2" * 60`` is
``"222222222222222222222222222222222222222222222222222222222222"``.

.. admonition:: Note

   If you count the characters in ``minutes`` (or use ``len(minutes)``), you
   will find 60 copies of the substring ``hours``.

We fix the logic error by converting the user's input to the ``int`` data type.

.. sourcecode:: python
   :linenos:

   hours = int(input('Enter a number of hours: '))
   print(hours, type(hours))
   minutes = hours * 60

   print('Number of minutes = ', minutes)

Running this with an input of ``3`` gives the output:

::

   Enter a number of hours: 3
   3 <class 'int'>
   Number of minutes =  180

Success!

Now that we found and fixed the logic error, the next step is to remove the
``print`` statement on line 2. It is not necessary for the normal running of
the program.

.. admonition:: Warning
   
   After debugging, be sure to remove ALL of the ``print`` statements used to
   find and fix logic errors.
