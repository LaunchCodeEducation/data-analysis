Exercises: Classes and Objects Solutions
========================================

Part 1: Create a New Class
--------------------------

.. _add-properties:

Add Properties to ``Robot``
^^^^^^^^^^^^^^^^^^^^^^^^^^^

#. Inside the class, define the ``__init__`` method. It should include
   parameters for ``self``, ``name``, ``mass``, and ``year``.

.. sourcecode:: python

   class Robot:
      def __init__(self, name, mass, year = 1984):
         self.name = name
         self.mass = mass
         self.year = year
         self.distance = 0

.. admonition:: Tip

   Before you move on, test your new class!
   
   .. sourcecode:: python

      main()

         test_bot = Robot()
         test_bot.name = "Rosie"
         print(test_bot.name)

   **Output**

   .. sourcecode:: python

      Rosie

:ref:`Return to Exercises<objects-and-classes-exercises1A>`

.. _add-methods:

Add Methods to ``Robot``
^^^^^^^^^^^^^^^^^^^^^^^^

#. Below ``__init__``, define a second method called ``move()``. This method
   should:

   #. Only take the ``self`` parameter.
   #. Generate a random number of steps (1 - 10) for the object to take. The
      range should include ``1`` and ``10`` as options. 

      .. sourcecode:: python

         def move(self):
            steps_taken = random.randint(1,10)
            
   #. Increase the ``distance`` property by the number of steps.
   #. Return the random number of steps.

#. Add the ``__str__`` method to return a string of the object properties.
   ``print(robot_name)`` should produce something like:

.. sourcecode:: python

   def __str__(self):
      output = "\nRobot Info: \n   Name: {0}\n   Mass: {1} kg\n   Year made: {2}\n   Distance traveled: {3}"
      return output.format(self.name, self.mass, self.year, self.distance)    

:ref:`Return to Exercises<objects-and-classes-exercises1B>`

Part 2: Create Objects
----------------------

You now have 4 total robots. Add another statement in ``main()`` where you
place the objects inside a list. Assign the collection to a variable called
``robots``.

.. sourcecode:: python

   def main():
      bot_1 = # Your arguments here...
      bot_2 = # Your arguments here...
      bot_3 = # Your arguments here...
      bot_4 = # Your arguments here...

      robots = [bot_1, bot_2, bot_3, bot_4]

.. _update-distances:

Update Distances
^^^^^^^^^^^^^^^^

Use a loop to iterate through the ``robots`` list. For each object, assign a
random value to the ``distance`` property, from ``1000`` to ``3000`` steps.

.. sourcecode:: python

   for robot in robots:
      robot.distance = random.randint(1000, 3000)


:ref:`Return to Exercises<objects-and-classes-exercises2>`


.. _oldest-robot:

Part 3: Find Oldest Robot
-------------------------

Between the class and ``main()``, define a function called ``oldest_robot``. It
should:

#. Accept a list of robots as a parameter.
#. Use a loop to iterate through the list.
#. Return the index value for the oldest robot in the list. 

   .. sourcecode:: python

      def oldest_robot(robot_list):
         robot_year = []
         for robot in robot_list:
            robot_born = robot.year
            robot_year.append(robot_born)
         oldest = robot_year.index(min(robot_year))

#. If two robots have the same ``year`` value, then the one with the largest
   ``distance`` will be older.

   .. sourcecode:: python

      oldest_robot_year = robot_year[oldest]
      oldest_robot_distance = robot_list[oldest].distance
      same_year = robot_year.count(oldest_robot_year)

      if same_year > 1:
         for index in range(len(robot_list)):
            year = robot_list[index].year

            if year == oldest_robot_year:
               if robot_list[index].distance > oldest_robot_distance:
                  oldest_robot_distance = robot_list[index].distance
                  oldest = index

:ref:`Return to Exercises<objects-and-classes-exercises3>`

.. _robot-race:

Part 4: Robot Races
-------------------

Now it's time for the robots to compete against each other! Define the
``robot_race`` function that takes a list of robots as a parameter.

Within the function:

#. Each robot takes a turn running a race.
#. A robot runs the race by calling its ``move()`` method several times.
#. A robot is done with the race when it moves 30 steps or more.
#. Create a new list to store how many turns it takes each robot to complete
   the race. Use the string: ``'____ took ____ turns to take 30 steps.'``
   Fill in the blanks with the robot’s name and race result.

   .. sourcecode:: python

      def robot_race(robot_list):
         results = []
         for robot in robot_list: 
            steps = 0
            turns = 0
         while steps <= 30:
            steps += robot.move()
            turns += 1
            results.append(f"{robot.name} took {turns} turns to take {steps} steps.")
         return results

:ref:`Return to Exercises<objects-and-classes-exercises4>`