.. _random-module:

The ``random`` Module
=====================

We often want to use random numbers in programs. Here are a few typical uses:

#. To play a game where the computer needs to throw some dice, pick a number,
   or flip a coin.
#. To select a random item from a list.
#. To randomly choose an event to apply to a virtual city.
#. To encrypt your banking session on the Internet.

Python provides a module called ``random`` that helps with tasks like this.

.. _pick-random-number:

Generate a Random Number
------------------------

Press the *Run* button a number of times for the program below. Note that the
printed values change each time. These are random numbers.

.. replit:: python
   :slug: RandomModule01
   :linenos:

   import random

   for number in range(5):
      random_value = random.random()
      print(random_value)

.. index:: ! random(), ! randint()

The **random()** function returns a float value in the range 0.0 - 1.0
(including 0.0 but not 1.0). If we need a larger float result,
say from 0.0 to 10.0, we simply multiply the result from ``random()`` by the
top value we want.

In the case shown below, we’ve converted the result from ``random()`` to a
number in the range 0.00 - 4.99. Press the *Run* button several times to
confirm the results, then try changing line 4 to produce a different range.

#. What happens if we change the multiplier?
#. What happens if we add a number to ``random.random()`` instead of
   multiplying?
#. What if we multiply ``random.random()`` by a value and then add a number to
   the result?

.. replit:: python
   :slug: RandomModule02
   :linenos:

   import random

   for number in range(5):
      random_value = random.random()*5
      print(round(random_value, 2))

The **randint()** function is a useful modification of ``random()``. It
generates an integer between the two arguments. In this case, however, the
results include both end points.

Run this program several times to check the behavior of the ``randint()``
function.

.. replit:: python
   :slug: RandomModule03
   :linenos:

   import random

   # Randomly generate whole number values from 80 - 90:
   for number in range(8):
      random_value = random.randint(80, 90)
      print(random_value)

Try changing the arguments inside the ``()`` to see how that affects the
numbers produced.

Not *Really* Random
^^^^^^^^^^^^^^^^^^^

It is important to note that random number generators are based on
*algorithms*. This means that the results are predictable and not truly random.

.. index:: ! seed value

Each algorithm starts with a **seed value**, which the code uses to create a
result. Every time we ask for another random number, we get one based on the
current seed, and the value of the seed gets updated. If we figure out how the
seed values are generated, then we can predict what the next "random" result
will be.

The good news is that each time we run the program, the seed value is likely
to be different (for example, the number of seconds since midnight). This means
that even though the random numbers come from following an algorithm, we will
likely get random behavior each time we run our program.

.. admonition:: Note

   Theoretically, if you could figure out the algorithm and seed values for a
   lottery game, then you could always pick the winning numbers!

   Doing this would be really, really hard, however.

.. _random-collection-item:

Select an Item from a Collection
--------------------------------

.. index:: ! choice()

Another useful function from the ``random`` module is the ``choice()``
function. It selects a random item from a string, list, or other collection.

Run the following program several times to see how this works:

.. replit:: python
   :slug: RandomModule04
   :linenos:

   import random

   word = "Abbreviation"
   numbers = [1, 3, 5, 7, 9, 111, 222, 333]

   for turn in range(5):
      character_choice = random.choice(word)
      number_choice = random.choice(numbers)
      print("The character is '{0}', and the number is {1}.".format(character_choice, number_choice))

We could do the same thing with ``randint()`` and bracket notation, but the
``choice()`` function wraps this up into a simple shortcut.

.. sourcecode:: Python
   :linenos:

   import random

   colors = ['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet']

   # Select a random integer from 0 - 6:
   index = random.randint(0, len(colors)-1)

   # Save the random element from the list:
   color_choice = colors[index]

Check Your Understanding
------------------------

.. admonition:: Question

   Which of the following shows the correct code to return the result of
   rolling a 6-sided dice?

   a. ``random.randint(0, 7)``
   b. ``random.randint(1, 7)``
   c. ``random.randint(0, 6)``
   d. ``random.randint(1, 6)``

.. Answer = d

.. admonition:: Question

   One reason that lotteries don’t use computers to pick the winning numbers
   is:

   a. There is no computer on the stage for the drawing.
   b. Computers don’t really generate random numbers.
   c. Computers would generate the same numbers for each drawing.
   d. The computer can’t tell what values were already selected, so it might repeat the same number several times.

.. Answer = b


