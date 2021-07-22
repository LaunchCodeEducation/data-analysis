Studio: Classes and Objects
============================

Now its time to design a new class of robots. These objects will all be able to
clean our school building, but we want to pick the best ones.

Let's create a class to handle new cleaning crew candidates!

Before You Start
----------------

.. admonition:: Tip

   We always encourage you to use local development at every opportunity. However, sometimes computers and software fail and we would rather you spend your studio time coding!
   If your computer is not cooperating with cloning your repo from Github, you can fork the starter code for the studio on `Replit <https://replit.com/@launchcode/ClassesStudio#main.py>`__.

Part 1: Add Class Properties and ``__str__`` Method
---------------------------------------------------

#. Declare a class called ``CrewCandidate`` with an ``__init__`` that takes
   three parameters: ``name``, ``mass``, and ``scores``. Note that ``scores``
   will be a list of test results for the candidate's speed and accuracy.
#. In ``main()``, create objects for the following candidates:

   a. iClean has a mass of 13.5 kg and test scores of 88, 85, and 90.
   b. Shiny has a mass of 1.5 kg and test scores of 93, 88, and 97.
   c. DustVac has a mass of 22.5 kg and test scores of 75, 78, and 62.

#. Define a ``__str__`` method to display the properties of each candidate. The
   output should look something like:

   ::

      **Candidate Information**
      Name: Shiny
      Mass: 1.5 kg
      Scores: [93, 88, 97]

#. Print each object to check to see if your class correctly assigns and
   displays the property values. (You can remove or comment out the ``print``
   statement after your tests pass).

Part 2: Add Another Class Method
--------------------------------

As our candidates complete more tests, we need to be able to add the new
scores to their records.

#. Create an ``add_score`` method in ``CrewCandidate``. The function must take
   a new score as a parameter in addition to ``self``.
#. When passed a score, the function adds the value to ``self.scores`` with the
   :ref:`append method <list-append-examples>`.

   .. admonition:: Tip

      Inside the class, the name of the list is ``self.scores`` instead of
      ``scores``. Thus, ``self.scores.append()`` is the proper syntax.

#. In ``main()``, test your new method by adding a score of ``83`` to iClean's
   record. Print out the new score list with ``object_name.scores``.

Part 3: Add More Methods
------------------------

Now that we can add scores to our candidates' records, we need to evaluate
their fitness for our cleaning program. Let's add two more methods to
``CrewCandidate``. One will average the test scores, and the other will decide
if the candidate should be added to the cleaning team.

Calculating the Test Average
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. TODO: Check reference to round function

#. Define an ``average()`` method. It only needs the ``self`` parameter.
#. To find the average, add up the entries from ``self.scores``, then divide
   the sum by the number of scores in the list.
#. To make the average easier to look at,
   round it to 1 decimal place, then return the result
   from the method.

Check your code by evaluating and printing Shiny's average test score
(``92.7``).

Determining Candidate Status
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Candidates with averages at or above 90% are automatically added to our new
cleaning crew. Backup robots average between 80 - 89%, while robots with
averages between 70 - 79% get sent out for repairs. Averages below 70% lead to
a short trip to the recycling bin.

#. Add a ``status()`` method to ``CrewCandidate``. The method returns a string
   (``'Accepted'``, ``'Backup'``, ``'Maintenance'``, or ``'Scrapped'``)
   depending on a candidate's average.
#. The ``status`` method requires the average test score. Fortunately, methods
   can call other methods inside a class! Just remember to use
   ``self.method_name()``.
#. Once ``status`` has a candidate's average score, return the proper string
   based on that value.
#. In ``main()``, test the ``status`` method on each of the three candidates.
   Print the result with the format, ``'___ scored an average of ___% (___).'``

   ::

      iClean scored an average of 87.7% (Backup).
      Shiny scored an average of 92.7% (Accepted).
      DustVac scored an average of 71.7% (Maintenance).

Part 4: Play a Bit
------------------

Use the class methods to boost DustVac's status to ``Backup`` or higher. How
many good tests will it take to reach ``Backup`` status? How many to reach
``Accepted``?

Note that scores cannot exceed 100%.

.. admonition:: Tip

   Rather than adding one score at a time, could you use a loop?
