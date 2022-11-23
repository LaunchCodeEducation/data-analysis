.. _data-and-variables-exercise-solutions:

.. _data-and-variables-exercise-solutionsA:

Exercise Solutions: Data and Variables
======================================

A. **Declare and assign variables**

   Declare and assign a variable for each item in the list.

   .. sourcecode:: py
      :linenos:

      shuttle_name = 'Determination'
      shuttle_speed_mph = 17500
      distance_to_mars_km = 225000000
      distance_to_moon_km = 38400
      MILES_PER_KM = 0.621

   :ref:`Back to the exercises <exercises-data-and-variables-partA>`


C. **Calculate a space mission!**

   We need to determine how many days it will take to reach Mars.

   .. _data-and-variables-exercise-solutionsC1:

   #. Create and assign a miles to Mars variable. You can get the miles to Mars
      by multiplying the distance to Mars in kilometers by the miles per
      kilometer.

      .. sourcecode:: py

         miles_to_mars = kilometers_to_mars * MILES_PER_KM

      .. _data-and-variables-exercise-solutionsC2:

   #. Next, we need a variable to hold the hours it would take to get to Mars.
      To get the hours, you need to divide the miles to Mars by the
      shuttle's speed.

      .. sourcecode:: py

         hours_to_mars = miles_to_mars / shuttle_speed_mph

      .. _data-and-variables-exercise-solutionsC3:

   #. Finally, declare a variable and assign it the value of days to Mars. In
      order to get the days it will take to reach Mars, you need to divide the
      hours it will take to reach Mars by 24.

      .. sourcecode:: py

         days_to_mars = hours_to_mars / 24

   :ref:`Back to the exercises <exercises-data-and-variables-partC>`

.. _data-and-variables-exercise-solutionsE:

E. **Now calculate a trip to the Moon**

   Repeat the calculations, but this time determine the number of days it would
   take to travel to the Moon and print to the screen a sentence that says
   ``"_____ will take ___ days to reach the Moon."``.

   .. sourcecode:: py
      :linenos:

      miles_to_moon = kilometers_to_moon * MILES_PER_KM
      hours_to_moon = miles_to_moon / shuttle_speed_mph
      days_to_moon = hours_to_moon / 24
      print(shuttle_name + " will take " + days_to_moon + " days to reach the Moon.")

   :ref:`Back to the exercises <exercises-data-and-variables-partE>`
