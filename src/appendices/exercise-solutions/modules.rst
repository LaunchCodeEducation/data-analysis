Exercise Solutions: Modules
===========================

Import Module Code
------------------

#. In ``main.py``, add a statement to import all functions from the
   ``averages`` module.

   .. sourcecode:: py

      import averages

3. Use the ``as`` keyword to rename the imported ``print_all`` function to
``display_results``.

   .. sourcecode:: py

      from display import print_all as display_results

Finish Coding A New Module
--------------------------

#. Add code to complete the ``random_from_list`` function. It should take a
   list as an argument and then return a
   :ref:`randomly selected element <random-collection-item>` from that list.

   .. sourcecode:: py
      :linenos:

      def random_from_list(a_list):
         # Your code here to select a random element from the list passed to the function.
         random_element = random.choice(a_list)
         return random_element# Return the selected element

Finish the Project
-------------------

#. **Line 19**: Call ``display_results`` to print all of the tests and student
   scores. Be sure to pass in the correct arguments.

   .. sourcecode:: py

      display_results(astronauts, test_titles, scores)

3. **Line 27**: Call ``average_for_student`` (with the proper arguments) to
print each astronaut's average score.

   .. sourcecode:: py

      avg = averages.average_for_student(astronaut_index,scores)
 