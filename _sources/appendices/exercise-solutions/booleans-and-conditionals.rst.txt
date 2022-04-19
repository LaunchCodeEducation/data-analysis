.. _booleans-and-conditionals-exercise-solutions:

Exercise Solutions: Booleans and Conditionals
=============================================

.. _booleans-and-conditionals-exercise-solutionsA:

A. **Assign the following variables for our space shuttle.**

   .. sourcecode:: py
      :linenos:

      engine_indicator_light = "red blinking"
      space_suits_on = True
      shuttle_cabin_ready = True
      crew_status = space_suits_on and shuttle_cabin_ready
      computer_status_code = 200
      shuttle_speed = 15000

   :ref:`Back to the exercises <exercises-booleans-and-conditionals>`

C. **Write conditional expressions to satisfy the safety rules.** 

   a. .. _booleans-and-conditionals-exercise-solutionsCa:

      .. sourcecode:: py
         :linenos:

         if crew_status:
            print("Crew Ready")
         else:
            print("Crew Not Ready")

   #. .. _booleans-and-conditionals-exercise-solutionsCb:

      .. sourcecode:: py
         :linenos:

         if computer_status_code == 200:
            print("Please stand by. Computer is rebooting.")
         elif computer_status_code == 400:
            print("Success! Computer online.")
         else:
            print("ALERT: Computer offline!")

   #. .. _booleans-and-conditionals-exercise-solutionsCc:

      .. sourcecode:: py
         :linenos:

         if shuttle_speed > 17500:
            print("ALERT: Escape velocity reached!")
         elif shuttle_speed < 8000:
            print("ALERT: Cannot maintain orbit!")
         else:
            print("Stable speed.")

   :ref:`Back to the exercises <exercises-booleans-and-conditionals>`

.. _booleans-and-conditionals-exercise-solutionsE:

E. **Monitor the shuttle's fuel status.**

   .. sourcecode:: py
      :linenos:

      if fuel_level < 1000 or engine_temperature > 3500 or engine_indicator_light == "red blinking":
         print("ENGINE FAILURE IMMINENT!")
      elif fuel_level <= 5000 or engine_temperature > 2500:
         print("Check fuel level. Engines running hot.")
      elif fuel_level > 20000 and engine_temperature <= 2500:
         print("Full tank. Engines good.")
      elif fuel_level > 10000 and engine_temperature <= 2500:
         print("Fuel level above 50%. Engines good.")
      elif fuel_level > 5000 and engine_temperature <= 2500:
         print("Fuel level above 25%. Engines good.")
      else:
         print("Fuel and engine status pending...")

   :ref:`Back to the exercises <exercises-booleans-and-conditionals>`