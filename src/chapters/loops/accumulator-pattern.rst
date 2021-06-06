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

   Recall that with ``range(start, end)``, the loop variable takes each value
   from ``start`` up to but NOT including ``end``. This is why line 4 uses
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

Building a String
^^^^^^^^^^^^^^^^^

The accumulator pattern also works on strings.

In the example below, we build a new string that contains only the vowels found
in a different string.

.. admonition:: Try It

   Follow the given steps to build the program!

   #. On line 3, define a variable called ``only_vowels`` and assign it the empty
      string, ``''``. This will be the *accumulator*, and it will get larger as
      the loop runs.
   #. On line 5, set up a ``for`` statement to loop through the characters in
      ``some_text``.

      .. sourcecode:: python
         :lineno-start: 5

         for character in some_text:

   #. Inside the loop, we want to check if ``character`` is a vowel. If
      ``True``, add ``character`` to ``only_vowels``. If ``False``, do not
      update ``only_vowels``. Paste this code into the loop. Remember to
      indent!

      .. sourcecode:: python
         :lineno-start: 6

         if character in 'aeiou':     # Check if char is a lowercase vowel.
            only_vowels += character  # If True, add char to only_vowels.
         
            print(only_vowels)

   #. The ``print`` statement displays the value of ``only_vowels`` each
      time it changes, and this allows us to see how the accumulator pattern
      works as the loop repeats.

   .. replit:: 
      :slug: AccumulatorPattern01
      :linenos:

      # Follow the instructions in the text to build this program!
      some_text = "bookkeeper anteater"

Properly done, the program should build up ``only_vowels`` as follows:

:: 

   o
   oo
   ooe
   ooee
   ooeee
   ooeeea
   ooeeeae
   ooeeeaea
   ooeeeaeae

Line 7 updates ``only_vowels`` with the ``+=`` operator. Each time the
statement runs, it adds a new character to the end of the string stored in the
variable.

Recall that ``only_vowels += character`` is a shortcut for the longer
expression ``only_vowels = only_vowels + character``. Is the order here
important?

.. admonition:: Try It!

   Replace line 7 with ``only_vowels = character + only_vowels`` and run the
   program again. What happened?

   By changing how we reassign the accumulator variable, we get different
   results.

.. _reverse-string:

Reversing a String
------------------

Let's look at another program that takes any string, reverses the characters,
and stores the new result in another variable.

Start by defining two variables---the string we want to reverse and a variable
to store the new string.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      old_string = "blue"
      reversed_string = ""  # This is our accumulator variable.

   Next, we loop through all the characters in ``old_string``. However, instead of
   adding each new character to the end of ``reversed_string``, we add it to the
   *beginning*.

   .. sourcecode:: python
      :linenos:

      old_string = "blue"
      reversed_string = ""  # This is our accumulator variable.

      for char in old_string:
         reversed_string = char + reversed_string
         # Line 5 adds reversed_string to the end of char.

      print(reversed_string)

   **Console Output**

   ::

      eulb

Let's break this program down step-by-step. This table shows the values of each
of our variables *after* each loop iteration.

.. list-table:: The accumulator pattern, step by step
   :header-rows: 1

   * - Loop iteration
     - ``char``
     - ``reversed_string``
   * - (before first iteration)
     - not defined
     - ``""``
   * - 1
     - ``"b"``
     - ``"b"``
   * - 2
     - ``"l"``
     - ``"lb"``
   * - 3
     - ``"u"``
     - ``"ulb"``
   * - 4
     - ``"e"``
     - ``"eulb"``

Decreasing Total
----------------

The accumulator pattern can also be used to *reduce* the size of a running
total.

.. admonition:: Example

   Run the program below several times using different values for ``total`` and
   ``decrease_by``

   .. replit::
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


