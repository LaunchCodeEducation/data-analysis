.. _exercises-booleans-and-conditionals:

Exercises: Booleans and Conditionals
====================================

Attempt these exercises to test your understanding. Don't worry if you struggle
while working on them. Struggling and then reviewing the material will help you
remember it.

Take note of any problem here or topic from this chapter that you don't understand. 
Take a break and return to the problem. Do you see it in a new way or have a better 
understanding? If not, try spending five minutes researching the topic. Start with this
book and if you still have questions, ask one on the internet or Slack/Discourse. 
You're not the first person to learn to code and you're definitely not the first person
to ask a question or get stuck!

`Code exercises A & B here <https://repl.it/@launchcode/ConditionalsExercises01Py>`__.

A. **Assign the following variables for our space shuttle**

   .. list-table::
      :widths: auto
      :header-rows: 1

      * - Variable Name
        - Value
      * - ``engine_indicator_light``
        - red blinking
      * - ``space_suits_on``
        - True
      * - ``shuttle_cabin_ready``
        - True
      * - ``crew_status``
        - ``space_suits_on`` and ``shuttle_cabin_ready``
      * - ``computer_status_code``
        - 200
      * - ``shuttle_speed``
        - 15000


   :ref:`Check your solution <booleans-and-conditionals-exercise-solutionsA>`. 

#. **Examine the code below. What will be printed to the console?**

   Use the value of ``engine_indicator_light`` defined above to answer this
   question.

   .. sourcecode:: py
      :linenos:

      if engine_indicator_light == "green": 
         print("engines have started")
      elif engine_indicator_light == "green blinking": 
         print("engines are preparing to start")
      else:
         print("engines are off")

   `Code exercises C & D here <https://repl.it/@launchcode/ConditionalsExercises02Py>`__.

#. **Write conditional expressions to satisfy the safety rules.** 

   Use the variables defined from the table above to satisfy the rules listed below.

   #. ``crew_status``

      - If the value is ``True``, print ``"Crew Ready"``
      - Else print ``"Crew Not Ready"``

      :ref:`Check your solution <booleans-and-conditionals-exercise-solutionsCa>`

   2. ``computer_status_code``

      - If the value is ``200``, print
        ``"Please stand by. Computer is rebooting."``
      - Else if the value is ``400``, print ``"Success! Computer online."``
      - Else print ``"ALERT: Computer offline!"``

      :ref:`Check your solution <booleans-and-conditionals-exercise-solutionsCb>`

   3. ``shuttle_speed``

      - If the value is ``> 17500``, print
        ``"ALERT: Escape velocity reached!"``
      - Else if the value is ``< 8000``, print
        ``"ALERT: Cannot maintain orbit!"``
      - Else print ``"Stable speed"``

      :ref:`Check your solution <booleans-and-conditionals-exercise-solutionsCc>`

#. **PREDICT**

   Do these code blocks produce the same result? Answer Yes or No.

   .. sourcecode:: py
      :linenos:

      if crew_status and computer_status_code == 200 and space_suits_on:
         print("all systems go")
      else:
         print("WARNING. Not ready")

   .. sourcecode:: py
      :linenos:

      if crew_status != True or computer_status_code != 200 or not(space_suits_on):
         print("WARNING. Not ready")
      else:
         print("all systems go")

   `Code exercises E & F here <https://repl.it/@launchcode/ConditionalsExercises03Py>`__.

#. **Monitor the shuttle's fuel status.**

   Implement the checks below using ``if`` / ``elif`` / ``else``
   statements. Order is important when working with conditionals, and the
   checks below are NOT written in the correct sequence. Please read ALL of the
   checks before coding and then decide on the best order for the conditionals.

   #. If ``fuel_level`` is above 20000 AND ``engine_temperature`` is at or below
      2500, print ``"Full tank. Engines good."``
   #. If ``fuel_level`` is above 10000 AND ``engine_temperature`` is at or below
      2500, print ``"Fuel level above 50%.  Engines good."``
   #. If ``fuel_level`` is above 5000 AND ``engine_temperature`` is at or below
      2500, print ``"Fuel level above 25%. Engines good."``
   #. If ``fuel_level`` is at or below 5000 OR ``engine_temperature`` is above
      2500, print ``"Check fuel level. Engines running hot."``
   #. If ``fuel_level`` is below 1000 OR ``engine_temperature`` is above 3500 OR
      ``engine_indicator_light`` is red blinking, print ``"ENGINE FAILURE
      IMMINENT!"``
   #. Otherwise, print ``"Fuel and engine status pending..."``

   .. admonition:: Try It

      Run your code several times to make sure it prints the correct phrase for
      each set of conditions.

      .. list-table::
         :widths: auto
         :header-rows: 1

         * - **fuel_level**
           - **engine_temperature**
           - **engine_indicator_light**
           - **Result**
         * - Any
           - Any
           - ``red blinking``
           - ``ENGINE FAILURE IMMINENT!``
         * - 21000
           - 1200
           - NOT ``red blinking``
           - ``Full tank. Engines good.``
         * - 900
           - Any
           - Any
           - ``ENGINE FAILURE IMMINENT!``
         * - 5000
           - 1200
           - NOT ``red blinking``
           - ``Check fuel level. Engines running hot.``
         * - 12000
           - 2600
           - NOT ``red blinking``
           - ``Check fuel level. Engines running hot.``
         * - 18000
           - 2500
           - NOT ``red blinking``
           - ``Fuel level above 50%. Engines good.``

   :ref:`Check your solution <booleans-and-conditionals-exercise-solutionsE>`

#. **Final bit of fun!**

   The shuttle should only launch if the fuel tank is full and the engine check
   is OK. *However*, let's establish an override command to ignore any warnings
   and send the shuttle into space anyway!

   #. Create the variable ``command_override``, and set it to be ``true`` *or*
      ``false``.

      If ``command_override`` is ``False``, then the shuttle should only launch
      if the fuel and engine check are OK.

      If ``command_override`` is ``True``, then the shuttle will launch
      regardless of the fuel and engine status.

   #. Code the following ``if`` / ``else`` check:

      If ``fuel_level`` is above 20000 AND ``engine_indicator_light`` is NOT
      red blinking OR ``command_override`` is true print ``"Cleared to
      launch!"``

      Else print ``"Launch scrubbed!"``
