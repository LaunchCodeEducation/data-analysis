.. _lists-exercise-solutions:

Exercise Solutions: Lists
=========================

.. _lists-exercise-solutions1:

Part One: Adding and Removing Items
-----------------------------------

.. _lists-exercise-solutions1a:

#. Create a list called ``adding_practice`` with a single entry: ``273.15``.
   Use the ``append`` method to add the following elements to the list one at a
   time. Print the list after each step to confirm the changes.

   a. 42

   .. sourcecode:: python

      adding_practice.append(42)


   :ref:`Back to the exercises <exercises-lists>`.

#. Use concatenation to add these three items to
   the list all at once: ``[False, -4.6, '87']``.

   .. _lists-exercise-solutions1b:

   .. sourcecode:: python

      adding_practice += [False, -4.6, '87']

   .. _lists-exercise-solutions1c:

#. ``append``, ``insert``, ``pop``, and ``remove`` are used to add or remove
   elements from a list. *Bracket notation* can be used to modify any element
   within a list. Starting with the ``cargo_hold`` list

   ::

      ['oxygen tanks', 'space suits', 'parrot', 'instruction manual', 'meal packs', 'slinky', 'security blanket']
   
   write statements to do the following:

   #. Use bracket notation to replace ``'slinky'`` in the list with ``'space
      tether'``. Print the list to confirm the change.

      .. sourcecode:: python

         cargo_hold[5] = 'space tether'

   #. Remove the last item from the list with ``pop``. Print the element
      removed and the updated list.
   #. Remove the first item from the list with ``pop``. Print the element
      removed and the updated list.
   #. ``append`` and ``insert`` require arguments inside the ``()``. Add the
      items ``1138`` and ``'20 meters'`` to the the list---the number at the
      start and the string at the end. Print the updated list to confirm the
      changes.

      .. sourcecode:: python

         cargo_hold.append('20 meters')
         cargo_hold.insert(0, 1138) 


   #. ``remove`` the parrot from the cargo hold, then print the updated list.
   #. Use ``format()`` to print the final contents of the list and its length.
      ``"The list ___ contains ___ items."``

      .. sourcecode:: python

         output = "The list {0} contains {1} items."
         print(output.format(cargo_hold, len(cargo_hold)))


   :ref:`Back to the exercises <exercises-lists>`.

   .. _lists-exercise-solutions2a:

Part Two: Slices & Methods
--------------------------

#. Using the slice syntax ``list_name[start : end]`` you can either insert,
   replace, or remove items from a list. 

   Use slices to make the following changes to the final ``cargo_hold`` list
   from part 1. Be sure to print the list after each step to confirm your
   work.

   #. Insert the string ``'keys'`` at index 3 without replacing any other
      entries.
   #. Remove ``'instruction manual'`` from the list. (Hint: The ``index``
      method is helpful to avoid manually counting an index).
   #. Replace the elements at indexes 2 - 4 with the items ``'cat'``,
      ``'book'``, and ``'string cheese'``.

   .. sourcecode:: python

      cargo_hold[2:5] = ['cat', 'book', 'string cheese'] 

   :ref:`Back to the exercises <exercises-lists>`.

#. Some methods---like ``append`` and ``pop``---alter the original list,
   while others do not. Use the lists

   .. sourcecode:: python

      supplies_1 = ['duct tape', 'gum', 3.14, False, 6.022e23]
      supplies_2 = ['orange drink', 'nerf toys', 'camera', '42', 'Rutabaga']

   to see if taking a slice or using the ``reverse`` and ``sort`` methods
   changes the original list.

   .. _lists-exercise-solutions2b:

   #. Print a slice of the last 3 items from ``supplies_1``. Does slice alter
      the original list? Verify this by printing ``supplies_1`` after taking
      the slice.

      .. sourcecode:: python

         print('Before slice:', supplies_1)
         print('Slice:', supplies_1[-3:])
         print('After slice:', supplies_1)
         print("Conclusion: Taking a slice does NOT alter the original list!")


   #. ``reverse`` the first list, ``sort`` the second, and then print both
      lists. What is the difference between the two methods?
   #. Do ``reverse`` or ``sort`` alter the original lists?

   :ref:`Back to the exercises <exercises-lists>`.

.. _lists-exercise-solutions3a:

Part Three: Split, List, and Join
---------------------------------

#. The ``split`` method converts a string into a list, while the ``join``
   method does the opposite.

   #. Try it! Given the string ``phrase = 'In space, no one can hear you code.'``,
      see what happens when you print ``phrase.split()`` vs.
      ``phrase.split('e')`` vs. ``list(phrase)``. What is the purpose of the
      argument inside the ``()``?

      .. sourcecode:: python

         output = "Using {0}: {1}"
         print(output.format('.split()', phrase.split()))
         print(output.format(".split('e')", phrase.split('e')))
         print(output.format('list()', list(phrase)))


   #. Given the list ``my_list = ['B', 'n', 'n', 5]``, see what happens when
      you print ``''.join(my_list)`` vs. ``'a'.join(my_list)`` vs.
      ``'_'.join(my_list)``. What is the purpose of the argument inside the
      ``()``?

      .. _lists-exercise-solutions3b:

   #. We can take a string with *delimiters* (like commas) and convert it into
      a modifiable list. Try it! Split the string
      ``'water,space suits,food,plasma sword,batteries'`` at each comma,
      alphabetize the list with ``sort``, then combine the elements into a new
      string. Use a hyphen to join the elements together in the string.

      .. sourcecode:: python

         items = cargo_hold.split(',')
         items.sort()
         new_string = '-'.join(items)
         print(new_string)


   #. Do ``split``, ``list``, or ``join`` change the original string/list?

   :ref:`Back to the exercises <exercises-lists>`.

.. _lists-exercise-solutions4a:

Part Four: Multi-dimensional Lists
----------------------------------

#. Lists can hold different data types, even other lists! A
   *multi-dimensional list* is one with entries that are also lists.

   #. Define and assign the following lists, which hold the name, chemical
      symbol and mass for different elements:

      i. ``element_1 = ['hydrogen', 'H', 1.008]``
      ii. ``element_2 = ['helium', 'He', 4.003]``
      iii. ``element_26 = ['iron', 'Fe', 55.85]``

   #. Define the list ``table``, and use ``table.append(list_name)`` to add each
      of the element lists to it. Print ``table`` to see its structure.

      .. sourcecode:: python

         table = []
         table.append(element_1)
         table.append(element_2)
         table.append(element_26)

      :ref:`Back to the exercises <exercises-lists>`.

   #. Use bracket notation to examine the difference between printing
      ``table[1]`` and ``table[1][1]``. Don't just nod your head! I want to
      HEAR you describe this difference. Go ahead, talk to your screen.
   
   .. _lists-exercise-solutions4b:
   
   #. Using bracket notation and the ``table`` list, print the mass from
      ``element_1``, the name from ``element_2`` and the symbol from
      ``element_26``.
      
      .. sourcecode:: python

         output = "To get the {0} from {1}, the syntax is {2}. Result = {3}."
         print(output.format('mass', 'element_1', 'table[0][2]', table[0][2]))

      :ref:`Back to the exercises <exercises-lists>`.

   #. ``table`` is an example of a *2-dimensional list*. The first "level"
      contains the element lists, and the second level holds the
      name/symbol/mass values.  
   #. **Optional:** Create a 3-dimensional list and
      print out one entry from each level in the list.

      :ref:`Back to the exercises <exercises-lists>`.

