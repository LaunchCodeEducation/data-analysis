.. _modules-exercises:

Exercises: Modules
==================

Practice makes better. You will create a program that accomplishes the
following:

a. Steps through a list of Yes/No questions.
b. Calls functions based on the user's responses.

Rather than coding all of the functions from scratch, you are going to use
existing modules to help assemble your project.

Open this `repl <https://replit.com/@launchcode/Modules-Exercises#main.py>`__ and *Fork* before getting started.

Import Module Code
------------------

Lucky you! Most of the functions you need are in the ``averages.py`` and
``display.py`` files.

#. In ``main.py``, add a statement to import all functions from the
   ``averages`` module.
#. In ``main.py``, add code to import ONLY the ``print_all`` function from
   the ``display`` module.
#. Use the ``as`` keyword to rename the imported ``print_all`` function to
   ``display_results``.

:ref:`Check Your Solutions<import-module-code>`

Finish Coding A New Module
--------------------------

``random_select.py`` requires your attention.

#. Add code to complete the ``random_from_list`` function. It should take a
   list as an argument and then return a
   :ref:`randomly selected element <random-collection-item>` from that list.
#. Import the ``random_select`` module into the ``main.py`` program.

.. admonition:: Note

   If you add any loose statements in the ``random_select.py`` file, remember
   to place them into a ``main()`` function.

:ref:`Check Your Solutions<finish-new-module>`

Finish the Project
-------------------

Now complete the project code.

.. admonition:: Note

   The line references given below assume that you added no blank lines during
   your work in the previous sections. If you did, do not worry. The comments
   in ``main.py`` will still show you where to add code.

#. **Line 19**: Call ``display_results`` to print all of the tests and student
   scores. Be sure to pass in the correct arguments.

   :ref:`Check Your Solutions<finish-project-1>`

#. **Line 23**: Using dot notation, call ``average_for_test`` to print the
   class average for each test. Use ``title_index`` and ``scores`` as
   arguments.
#. **Line 27**: Call ``average_for_student`` (with the proper arguments) to
   print each astronaut's average score.

   :ref:`Check Your Solutions<finish-project-2>`

#. **Line 30**: Call ``random_from_list`` to pick the next spacewalker from the
   ``astronauts`` list.

Sanity check!
--------------

Properly done, your output should look something like:

::

   Would you like to display all scores? Y/N: y
   Name        Math      Fitness   Coding    Nav       Communication
   Fox         95        86        83        81        76
   Turtle      79        71        79        87        72
   Cat         94        87        87        83        82
   Hippo       99        77        91        79        80
   Dog         96        95        99        82        70

   Would you like to average the scores for each test? Y/N: y
   Math test average = 92.6%.
   Fitness test average = 83.2%.
   Coding test average = 87.8%.
   Nav test average = 82.4%.
   Communication test average = 76%.

   Would you like to average the scores for each astronaut? Y/N: y
   Fox's test average = 84.2%.
   Turtle's test average = 77.6%.
   Cat's test average = 86.6%.
   Hippo's test average = 85.2%.
   Dog's test average = 88.4%.

   Would you like to select the next spacewalker? Y/N: y
   Turtle is the next spacewalker.

.. admonition:: Note

   In your output, the spacings for the test score columns will probably NOT
   line up perfectly. *This is OK*.

   When we learn how to display output in a window *other* than the console,
   we will worry about making columns look nice.
