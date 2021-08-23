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

.. raw:: html

   <iframe src="https://trinket.io/embed/python/a38187485a" width="100%" height="300" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

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

.. raw:: html

   <iframe src="https://trinket.io/embed/python/4a4752da5c" width="100%" height="300" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

The **randint()** function is a useful modification of ``random()``. It
generates an integer between the two arguments. In this case, however, the
results include both end points.

Run this program several times to check the behavior of the ``randint()``
function.

.. raw:: html

   <iframe src="https://trinket.io/embed/python/17a01e0a3e" width="100%" height="300" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

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

Another useful function from the ``random`` module is the **choice()**
function. It selects a random item from a string, list, or other collection.

Run the following program several times to see how this works:

.. raw:: html

   <iframe src="https://trinket.io/embed/python/09f0f7531e" width="100%" height="300" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>


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

.. admonition:: Try It!

   Randomly change the color of the turtle before it draws each side of the
   polygon!

   Add the statement ``bob.color(random.choice(colors))`` to the code below.

   .. raw:: html

      <iframe height="700px" width="100%" src="https://repl.it/@launchcode/Random-Turtle-Color?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

Random Turtle Walk
------------------

Let's have a little more turtle fun!

Up until now, we have always given a specific direction (``left`` or ``right``)
and angle whenever we turn a turtle. Lets throw in some random values to make
the path our turtle follows less predictable.

.. admonition:: Example

   Currently, the turtle takes 10 steps, and it always turns right by 90
   degrees. Run the program first to see this behavior.
   
   .. raw:: html

      <iframe height="700px" width="100%" src="https://repl.it/@launchcode/Random-Turtle-Walk?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

   Now make the following changes:

   #. At the start of the loop, define a ``coin_toss`` variable and assign it
      the result of ``random.randint(0,1)``. As the name of the variable tells
      us, we can treat this like a coin toss, with ``0`` standing for heads,
      and ``1`` standing for tails.
      
      If you don't like working with 0 and 1, you can use
      ``random.choice('heads', 'tails')`` instead. However, numbers are easier
      to work with, and you are less likely to mistype 0 and 1.
   #. Place the turn command inside a conditional as follows:

      .. sourcecode:: Python
         :lineno-start: 14

         if coin_toss == 0:
            bob.right(90)
         else:
            bob.left(90)
      
      Now ``bob`` turns left or right depending on the random choice of ``0`` or
      ``1``. Run the program several times and compare the paths.
   #. Next, let's make ``bob`` rotate by a random number of degrees. Replace the
      argument ``90`` with ``random.randint(0, 180)``. Run the program several
      times to see the result.
   #. Finally, randomly assign the number of steps ``bob`` takes to a value
      between 5 and 25. Run the program several times to check your work.

Here are some bonus tasks for you to try as well:

#. Add a ``colors`` list and randomly assign a color to the turtle before each
   line is drawn.
#. Randomly select the length of each line drawn.
#. Randomly change the speed before or during the turtle's walk.
#. Move the walking code into a ``random_walk`` function that takes a turtle
   and the number of steps as parameters. Call ``random_walk`` to make ``bob``
   move.
#. Add a second turtle and have it take a stroll as well.

.. figure:: figures/turtle-random-walk.png
   :alt: Image with two panels. The left panel shows a single, multi-color random turtle path. The right panel shows two multi-color, random turtle paths.

   A single, multi-color turtle path. Two multi-color paths drawn by different turtles.

Check Your Understanding
------------------------

.. admonition:: Question

   Which of the following shows the correct code to return the result of
   rolling a 6-sided dice?

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">random.randint(0, 7)</span></li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">random.randint(1, 7)</span></li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">random.randint(0, 6)</span></li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, true)"> <span style="color:#419f6a; font-weight: bold">random.randint(1, 6)</span></li>
      </ol>
      <p id="Q1"></p>

.. Answer = d

.. admonition:: Question

   One reason that lotteries don’t use computers to pick the winning numbers
   is:

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> There is no computer on the stage for the drawing.</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, true)"> Computers don’t really generate random numbers.</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> Computers would generate the same numbers for each drawing.</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> The computer can’t tell what values were already selected, so it might repeat the same number several times.</li>
      </ol>
      <p id="Q2"></p>

.. Answer = b


