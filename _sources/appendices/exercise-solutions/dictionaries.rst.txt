Exercise Solutions: Dictionaries
================================

Part A: Search a Dictionary
---------------------------

.. _dictionaries-exercise-solutions-A1:

1. Write a function called ``return_cost`` that takes a dictionary and flavor
   choice as parameters.

   a. The function searches the dictionary for the flavor and returns its cost.
   b. If the flavor is not in the dictionary, return a value of ``0``.

   .. sourcecode:: python
      :linenos:

      def return_cost(menu, item):
         if item in menu:        
            return menu[item]   
         return 0 

   :ref:`Back to the exercises <dictionaries-exercises-A1>`

.. _dictionaries-exercise-solutions-A3:

3. Write a function called ``fanciest_flavor`` that takes a dictionary as a
   parameter. The function should return the key name for the most expensive
   choice in the dictionary.  

   .. sourcecode:: py
      :linenos:

      def fanciest_flavor(menu): 
         highest_cost = 0
         fanciest = ''
         for (flavor, price) in menu.items():
            if price > highest_cost:    
                  fanciest = flavor       
                  highest_cost = price  
         return fanciest

   :ref:`Back to the exercises <dictionaries-exercises-A3>`

Part B: Keys from a Collection
------------------------------

.. _dictionaries-exercise-solutions-B1:

1. Write a function called ``assign_tickets`` that takes a list of names as a
   parameter.

   .. sourcecode:: py
      :linenos:

      def assign_tickets(names):

   :ref:`Back to the exercises <dictionaries-exercises-B1>`

.. _dictionaries-exercise-solutions-B3:

3. For the value of each key, assign a random integer from 100-500.

   .. sourcecode:: py

      tickets[name] = random.randint(100, 500)

   :ref:`Back to the exercises <dictionaries-exercises-B3>`

.. _dictionaries-exercise-solutions-B5:

5. In ``main()``, call the ``assign_tickets`` function and assign the result to a ``ticket_holders`` variable.

   .. sourcecode:: py

      ticket_holders = assign_tickets(names)

   :ref:`Back to the exercises <dictionaries-exercises-B5>`

Part C: Modify Values
---------------------

.. _dictionaries-exercise-solutions-C:

Call the function ``fix_tickets``, and use ``ticket_holders`` as the argument.
The ``fix_tickets`` function should:

#. Accept a dictionary as a parameter.
#. Loop through the dictionary and check each ticket number to see if it is in
   the range 100-199 (including the end points).
#. For a ticket within the range, increase its value by ``500`` and reassign it
   to the key.
#. Unless you cloned the dictionary, there is no need to return the updated
   collection.

.. sourcecode:: py
   :linenos:

   def fix_tickets(tickets):
      for (key, value) in tickets.items():
         if 100 <= value <= 199:   
               tickets[key] += 500   

:ref:`Back to the exercises <dictionaries-exercises-C>`

Part D: Counting Characters
---------------------------

.. _dictionaries-exercise-solutions-D:

Write a function called ``character_count`` that counts how many times each
character appears in a string.

The function should:

#. Accept a string as a parameter.
#. Create an empty dictionary called ``counts``.
#. Loop through the string and check each character.

   a. If the character does NOT exist in as a key in ``counts``, add it and
      assign it a value of ``1``.
   b. If the character DOES exist as a key in ``counts``, increase its value by
      one.

#. Return the completed ``counts`` dictionary and assign it to a ``results``
   variable in ``main()``.

.. sourcecode:: py
   :linenos:

   def character_count(a_string):
      counts = {}                     
      for char in a_string.lower():   
         if char in counts:          
               counts[char] += 1       
         else:
               counts[char] = 1        
      return counts  

:ref:`Back to the exercises <dictionaries-exercises-D>`

Part E: Use a List to Sort Key/Value Output
-------------------------------------------

.. _dictionaries-exercise-solutions-E1:

1. In the ``main()`` function, loop through the ``results`` dictionary and print each key/value pair on its own line.

   .. sourcecode:: py
      :linenos:

      for (key, value) in results.items():
         print(f"{key}: {value}")

   :ref:`Back to the exercises <dictionaries-exercises-E1>`

.. _dictionaries-exercise-solutions-E3:

3. Modify your code again, but this time display the character counts in alphabetical order.

   a. Use the ``list`` function to create a list of the keys from the
      ``results`` dictionary.
   b. Sort the list, then use a loop to print the key/value pairs, one pair
      per line.

   .. sourcecode:: py
      :linenos:

      keys = list(results.keys()) 
      keys.sort()

   :ref:`Back to the exercises <dictionaries-exercises-E3>`





