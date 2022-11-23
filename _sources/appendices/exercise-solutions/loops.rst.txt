.. _loops-exercise-solutions:

Exercise Solutions: Loops
==========================

.. _loops-exercise-solutions1:

``for`` Practice
-----------------

#. Construct ``for`` loops that accomplish the following tasks:

   a. Print the numbers 0 - 20, one number per line.

   .. sourcecode:: py
      :linenos:

      for i in range(21):
         print(i)

   c. Print the EVEN numbers 12 down to -14 in descending order, one number
      per line.

   .. sourcecode:: py
      :linenos:

      for i in range(12, -15, -2):
         print(i)


:ref:`Back to the exercises <exercises-loops>`.

.. _loops-exercise-solutions2:

``while`` Practice
-------------------

Define three variables for the LaunchCode shuttle---one for the starting
fuel level, another for the number of astronauts aboard, and the third for
the altitude the shuttle reaches.

1. Construct ``while`` loops to do the following:

   a. Prompt the user to enter the starting fuel level. The loop should continue until
      the user enters a positive value greater than 5000 but less than 30000.

   .. sourcecode:: py
      :linenos:

      fuel_level = 0
      num_astronauts = 0
      altitude = 0

      while fuel_level <= 5000 or fuel_level > 30000: 
         fuel_level = int(input("Enter the starting fuel level: "))

   c. Use a final loop to monitor the fuel status and the altitude of the
      shuttle. Each iteration, decrease the fuel level by 100 units for each
      astronaut aboard. Also, increase the altitude by 50 kilometers. (Hint:
      The loop should end when there is not enough fuel to boost the crew
      another 50 km, so the fuel level might not reach 0).

   .. sourcecode:: py
      :linenos:

      while fuel_level-100*num_astronauts >= 0:
        altitude += 50
        fuel_level -= 100*num_astronauts

#. After the loops complete, print the result with the phrase, ``The shuttle gained an altitude of ___ km and has ___ kg of fuel left.`` Fill in the blanks with the altitude and fuel level values.


   a. If the altitude is 2000 km or higher, add "Orbit achieved!"
   b. Otherwise add, "Failed to reach orbit."

   .. sourcecode:: py
      :linenos:

      if altitude >= 2000:
         ending = 'Orbit achieved!'
      else:
         ending = 'Failed to reach orbit.'

      print('The shuttle gained an altitude of', altitude, 'km and has', fuel_level,'kg of fuel left.', ending)

:ref:`Back to the exercises <exercises-loops>`.