.. _accumulator-pattern:

The Accumulator Pattern
=======================

.. index:: algorithm, ! pattern

Recall that an *algorithm* is a set of specific steps that, when followed,
solve a problem.

A **pattern** is similar to an algorithm, but it can be used to solve many
different types of problems. Think of a *pattern* like tying a knot---you can
use the same steps to tie your shoelaces, a drawstring, the handles of a
plastic bag, the ribbon on a present, etc. The pattern is the act of tying, and
it is part of a larger solution (e.g. cleaning up after your dog). Often, a
pattern makes up one piece of an algorithm.

Even though two algorithms can solve very different problems, the same pattern
might be found in each one.

Let's take a look at your first coding pattern.

Keeping a Running Total
-----------------------

Assume you are working at a theater, and your job is to count how many people
walk through the front door. To help you keep track of the total, your boss
gives you a counting tool. Every time a person walks in, you push a button and
*CLICK*, the total displayed on the tool increases by 1.

.. index:: ! accumulator pattern

This is an example of the **accumulator pattern**. Every time a particular
event occurs, the value of a running total gets updated.

In programming, the accumulator pattern occurs VERY often. The key pieces to
this pattern include:

#. A variable that starts at some basic value. For numbers, this value is
   usually ``0`` or ``1``. For the ``str`` data type, begin with the empty
   string, ``""`` or ``''``.
#. A loop.
#. Inside the loop, the value of the variable steadily increases (or decreases)
   with each iteration.

Let's look at some code to see how the accumulator pattern works.

Adding ``1...num``
^^^^^^^^^^^^^^^^^^

Let's write a program that adds up the numbers from 1 to ``num``, where the
variable ``num`` stores some integer.

If we did this with pencil and paper, finding the sum might look like this
when ``num = 6``:

::

   (1 + 2) + 3 + 4 + 5 + 6   # Calculate 1 + 2
   (3 + 3) + 4 + 5 + 6       # Calculate 3 + 3
   (6 + 4) + 5 + 6           # Calculate 6 + 4
   (10 + 5) + 6              # Calculate 10 + 5
   (15 + 6)                  # Calculate 15 + 6
   21                        # Final result!

In each step, the *running total* is the first number, and it gets added to the
next value in the series. As we move down the steps, we see the total increase
from 1 to 3 to 6 etc.

For larger values of ``num``, solving by hand gets tedious really fast. Loops
to the rescue!

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      num = 6
      total = 0

      for integer in range(1, num+1):
         total += integer

      print(total)

   **Console Output**

   ::

      21

   #. In line 2, we assign a value of ``0`` to the variable ``total``.
   #. Each time the loop repeats, the loop variable ``integer`` is assigned a
      new, higher value (1 to 6).
   #. Each time line 5 runs, the current value of ``integer`` is added to
      ``total``.
   #. Once the loop ends, ``total`` contains the sum of all the individual
      values.

.. admonition:: Note

   Recall that with ``range(start, stop)``, the loop variable takes each value
   from ``start`` up to but NOT including ``stop``. This is why line 4 uses
   ``range(1, num+1)``. We want to include the value of ``num`` as part of the
   iteration.

The loop carries out the same basic algorithm that we used to solve
``1 + 2 + 3 + 4 + 5 + 6`` by hand. When we do this on paper, we usually do not
write down a running total for simple steps like 1 + 2. With programming,
however, we must store this total in a variable.

.. index:: ! accumulator

.. index::
   single: pattern, accumulator

The variable ``total`` is called the **accumulator**, which is a fancy way of
saying that it gathers up all the individual integers one by one.

.. admonition:: Tip

   The key to using the accumulator pattern successfully is to define the
   accumulator variable *before* you start the loop. Once inside the loop,
   update the variable.

Decreasing Total
----------------

The accumulator pattern can also be used to *reduce* the size of a running
total.

.. admonition:: Example

   Run the program below several times using different values for ``total`` and
   ``decrease_by``

   .. replit:: py
      :slug: AccumulatorPattern02
      :linenos:

      # The accumulator pattern can also decrease a running total!
      total = 1000
      decrease_by = 25

      for step in range(10):
         total -= decrease_by

      print(total)

.. admonition:: Tip

   Any of the operators ``+=, -=, *=, /=`` can be used in the accumulator
   pattern to update the variable.

   Which operator you choose depends on the problem you need to solve.

Check Your Understanding
------------------------

Use this code sample to answer the following questions:

.. sourcecode:: python
   :linenos:

   total = 0

   for step in range(5):
      total += 2
   
   print(total)

.. admonition:: Question

   What does the program print?

   a. 0
   b. 2
   c. 5
   d. 10

.. Answer = d

.. admonition:: Question

   What will print if you put ``total = 0`` inside the for loop but before
   ``total += 2``?

   a. 0
   b. 2
   c. 5
   d. 10

.. Answer = b


