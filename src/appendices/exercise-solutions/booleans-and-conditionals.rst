.. _booleans-and-conditionals-exercise-solutions:

Exercise Solutions: Booleans and Conditionals
=============================================

.. _booleans-and-conditionals-exercise-solutionsA:

A. **Assign the following variables for our space shuttle.**

   .. sourcecode:: py
      :linenos:

      engineIndicatorLight = "red blinking"
      spaceSuitsOn = True
      shuttleCabinReady = True
      crewStatus = spaceSuitsOn and shuttleCabinReady
      computerStatusCode = 200
      shuttleSpeed = 15000

   :ref:`Back to the exercises <exercises-booleans-and-conditionals>`

C. **Write conditional expressions to satisfy the safety rules.** 

   a. .. _booleans-and-conditionals-exercise-solutionsCa:

      .. sourcecode:: py
         :linenos:

         if crewStatus:
            print("Crew Ready")
         else:
            print("Crew Not Ready")

   #. .. _booleans-and-conditionals-exercise-solutionsCb:

      .. sourcecode:: py
         :linenos:

         if computerStatusCode == 200:
            print("Please stand by. Computer is rebooting.")
         elif computerStatusCode == 400:
            print("Success! Computer online.")
         else:
            print("ALERT: Computer offline!")

   #. .. _booleans-and-conditionals-exercise-solutionsCc:

      .. sourcecode:: py
         :linenos:

         if shuttleSpeed > 17500:
            print("ALERT: Escape velocity reached!")
         elif shuttleSpeed < 8000:
            print("ALERT: Cannot maintain orbit!")
         else:
            print("Stable speed.")

   :ref:`Back to the exercises <exercises-booleans-and-conditionals>`

.. _booleans-and-conditionals-exercise-solutionsE:

E. **Monitor the shuttle's fuel status.**

   .. sourcecode:: py
      :linenos:

      if fuelLevel < 1000 or engineTemperature > 3500 or engineIndicatorLight == "red blinking":
         print("ENGINE FAILURE IMMINENT!")
      elif fuelLevel <= 5000 or engineTemperature > 2500:
         print("Check fuel level. Engines running hot.")
      elif fuelLevel > 20000 and engineTemperature <= 2500:
         print("Full tank. Engines good.")
      elif fuelLevel > 10000 and engineTemperature <= 2500:
         print("Fuel level above 50%. Engines good.")
      elif fuelLevel > 5000 and engineTemperature <= 2500:
         print("Fuel level above 25%. Engines good.")
      else:
         print("Fuel and engine status pending...")

   :ref:`Back to the exercises <exercises-booleans-and-conditionals>`