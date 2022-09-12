.. _exercises-loops:

Exercises: Loops
================

.. pull-quote::

   Practice makes better. Repetition is a good thing.

   Repetition is a good thing.

   Repetition is a good thing.

   Repetition is a good thing.

WAIT!!!  Why type "Repetition is a good thing," four times when we can code
a better result?  How about printing the phrase 100 times instead?

.. sourcecode:: py
   :linenos:

    for i in range(101):
        print("Repetition is a good thing.")

Loops simplify repetitive tasks!

``for`` Practice
-----------------

`Code it at repl.it <https://repl.it/@launchcode/ForLoopExercisesPy>`_

#. Construct ``for`` loops that accomplish the following tasks:

   a. Print the numbers 0 - 20, one number per line.
   b. Print only the ODD values from 3 - 29, one number per line.
   c. Print the EVEN numbers 12 down to -14 in descending order, one number
      per line.
   d. Print the numbers 50 down to 20 in descending order, but only
      if the numbers are multiples of 3.

   :ref:`Check your solution <loops-exercise-solutions1>`. 

``while`` Practice
-------------------

`Code it at repl.it <https://repl.it/@launchcode/WhileLoopExercisesPy>`__

Define three variables for the LaunchCode shuttle---one for the starting
fuel level, another for the number of astronauts aboard, and the third for
the altitude the shuttle reaches.

4. Construct ``while`` loops to do the following:

   a. Prompt the user to enter the starting fuel level. The loop should continue until
      the user enters a positive value greater than 5000 but less than 30000. 
   b. Use a second loop to query the user for the number of astronauts
      (up to a maximum of 7). Validate the entry by having the loop continue
      until the user enters an integer from 1 - 7.
   c. Use a final loop to monitor the fuel status and the altitude of the
      shuttle. Each iteration, decrease the fuel level by 100 units for each
      astronaut aboard. Also, increase the altitude by 50 kilometers. (Hint:
      The loop should end when there is not enough fuel to boost the crew
      another 50 km, so the fuel level might not reach 0).

#. After the loops complete, print the result with the phrase, ``The shuttle gained an altitude of ___ km and has ___ kg of fuel left.`` Fill in the blanks with the altitude and fuel level values.

   #. If the altitude is 2000 km or higher, add "Orbit achieved!"
   #. Otherwise add, "Failed to reach orbit."

      :ref:`Check your solution <loops-exercise-solutions2>`. 

Submitting Your Work
--------------------

When finished copy the URLs to your repls for the exercises, separating each URL with a semi-colon and paste them into the submission box in Canvas for **Exercises: Booleans, Conditionals, and Loops** and click *Submit*.

You should have a total of **5** repls, **2** from the above Loops Exercises and **3** from from :ref:`Booleans and Conditionals Exercises<exercises-booleans-and-conditionals>`.
