.. _data-and-variables-exercise-solutions:

.. _data-and-variables-exercise-solutionsA:

Exercise Solutions: Data and Variables
======================================



A. **Declare and assign variables**

   Declare and assign a variable for each item in the list.

   .. sourcecode:: py
      :linenos:

      shuttleName = 'Determination'
      shuttleSpeedMph = 17500
      distanceToMarsKm = 225000000
      distanceToMoonKm = 38400
      milesPerKilometer = 0.621

   :ref:`Back to the exercises <exercises-data-and-variables-partA>`



C. **Calculate a space mission!**

   We need to determine how many days it will take to reach Mars.

   .. _data-and-variables-exercise-solutionsC1:

   #. Create and assign a miles to Mars variable. You can get the miles to Mars
      by multiplying the distance to Mars in kilometers by the miles per
      kilometer.

      .. sourcecode:: py

         milesToMars = kilometersToMars * milesPerKilometer

      .. _data-and-variables-exercise-solutionsC2:

   #. Next, we need a variable to hold the hours it would take to get to Mars.
      To get the hours, you need to divide the miles to Mars by the
      shuttle's speed.

      .. sourcecode:: py

         hoursToMars = milesToMars / shuttleSpeedMph

      .. _data-and-variables-exercise-solutionsC3:

   #. Finally, declare a variable and assign it the value of days to Mars. In
      order to get the days it will take to reach Mars, you need to divide the
      hours it will take to reach Mars by 24.

      .. sourcecode:: py

         daysToMars = hoursToMars / 24

   :ref:`Back to the exercises <exercises-data-and-variables-partC>`

.. _data-and-variables-exercise-solutionsE:

E. **Now calculate a trip to the Moon**

   Repeat the calculations, but this time determine the number of days it would
   take to travel to the Moon and print to the screen a sentence that says
   ``"_____ will take ___ days to reach the Moon."``.

   .. sourcecode:: py
      :linenos:

      milesToMoon = kilometersToMoon * milesPerKilometer
      hoursToMoon = milesToMoon / shuttleSpeedMph
      daysToMoon = hoursToMoon / 24
      print(shuttleName + " will take " + daysToMoon + " days to reach the Moon.")

   :ref:`Back to the exercises <exercises-data-and-variables-partE>`
