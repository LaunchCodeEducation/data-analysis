Assignment #2: Scrabble Scorer
==============================

For your second assignment, we'll ask you to modify and improve our Scrabble Scorer program. 

We want you to update our program that asks a user for a word 
and outputs a score. Your final version will have three scoring algorithms and 
allow a user to interactively choose which algorithm to use. We've provided some starter code that
includes the official Scrabble scoring point system and we'd like you to make 
some modifications to improve it.

Let's roll.

Requirements
------------

.. admonition:: Note

   The requirements below are what your assignment should look like when it's 
   time to submit. Rome wasn't built in a day and neither was Scrabble.

   This assignment is broken down so you can complete small pieces as you go.
   You need to move sequentially starting with Part A below. You'll have a much more 
   enjoyable time writing this program if you read this entire page before even opening repl.it.

#. Write an ``initial_prompt()`` function that asks a user to input a word.
#. Have the program return a score for the word using ``old_scrabble_scorer()``.
#. Add additional scoring algorithms and store them in the ``scoring_algorithms`` list.
#. Create a ``transform()`` function that takes in the ``OLD_POINT_STRUCTURE``
   object and returns a ``new_point_structure`` object.
#. Use the ``run_program()`` function to serve as the starting point for your
   program.

Starter Code
------------

Follow your Canvas instructions for creating your solution repository from the template starter application.

You only need to code in one file here, ``scrabble-scorer.py``. Within this Python
file are the starts of all of the functions and data sctructures you need to write your 
Scrabble Scorer program.

You'll run the application from ``index.py``. Running the starter code without any modifications
results in:

:: 

   Let's play some Scrabble!


.. admonition:: Tip

   If you don't see this message printed and have exhausted your troubleshooting skills, 
   reach out to your classmates or course staff ASAP so you can get started with the real coding.

Instructions
------------

A) Initial Prompt
^^^^^^^^^^^^^^^^^

#. Modify the provided ``initial_prompt()`` function to prompt the user to enter a word to score. The function should return 
   the text inputted by the user.
#. Use the ``old_scrabble_scorer()`` function provided to score the word provided by the user. To do this,
   invoke ``old_scrabble_scorer()`` inside of the final function in the file, ``run_program()``. 
   ``old_scrabble_scorer()`` will take the return value of ``initial_prompt()``.
   Print the result.

Before you move on, be sure you're on the right track. At this point, your program should have an output like this:

:: 

   Let's play some Scrabble!

   Enter a word to score: pineapple
   Points for 'P': 3
   Points for 'I': 1
   Points for 'N': 1
   Points for 'E': 1
   Points for 'A': 1
   Points for 'P': 3
   Points for 'P': 3
   Points for 'L': 1
   Points for 'E': 1



B) Add and Organize Scoring Algorithms
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Your job here is to write two other scoring algorithms for the Scrabble player.

#. ``simple_scorer``: Define a function that takes a word as a parameter and
   returns a numerical score. Each letter within the word is worth 1 point.
#. ``vowel_bonus_scorer``: Define a function that takes a word as a parameter and
   returns a score. Each vowel within the word is worth 3 points, and each
   consonant is worth 1 point.

.. admonition:: Note

   Make each scoring algorithm case *insensitive*, meaning that they
   should all ignore case when assigning points.


Once you've written these scoring functions, organize all three of the scoring options into a tuple 
called ``scoring_algorithms``. Your program will use this tuple to retrieve information about the 
three scoring algorithms and convey that information to the user. 

#. Finish writing the ``scoring_algorithms`` tuple. It should be populated with three dictionary objects, 
   one for each of the three scoring options. Each dictionary should contain three keys: ``name``, ``description``, and ``scoring_function``.
#. Examine the table for the information to store in ``name`` and
   ``description``. The ``scoring_function`` for each object should be the name of
   one of the three scoring algorithms already defined.

   .. list-table::
      :header-rows: 1

      * - Name
        - Description
        - Score Function
      * - Simple Score
        - Each letter is worth 1 point.
        - A function with a parameter for user input that returns a score.
      * - Bonus Vowels
        - Vowels are 3 pts, consonants are 1 pt.
        - A function that returns a score based on the
          number of vowels and consonants.
      * - Scrabble
        - The traditional scoring algorithm.
        - Uses the ``old_scrabble_scorer()`` function to determine the score for a given
          word.


#. Finish writing ``scorer_prompt()`` so that the user can select which scoring algorithm to use when the program scores their word. 
   Use the selected algorithm to determine the score for the word:

   a. If the user enters ``0``, have the program output a score using the simple scorer.
   b. If the user enters ``1``, use the vowel bonus scoring function.
   c. If the user enters ``2``, use the Scrabble scoring option.

   ``scorer_prompt()`` should return the whole dictionary object the user has selected.

#. Inside of ``run_program()``, remove the ``old_scrabble_scorer()`` call. Replace it with a call to ``scorer_prompt()`` so that the program asks the user for a scoring algorithm after prompting for a word.
   Use the scoring object returned from ``scorer_prompt()`` to score the user's word and let the user know what score their word receives.


   .. admonition :: Tip

      Your ``scoring_algorithms`` structure now holds all of the scoring information required for the program.

      Use bracket notation to access a scoring dictionary and its key-value pairs.

      .. admonition:: Example

         .. sourcecode:: python

            # Simple scoring
            print("algorithm name: ", scoring_algorithms[0]["name"])
            scoring_function = scoring_algorithms[0]["scorer_function"]
            print(scoring_function("Python"))

         **Output**

         ::

            algorithm name:  Simple Score
            scoring_function result:  6

Before moving forward, your running program should behave roughly like this:

:: 

   Let's play some Scrabble!

   Enter a word to score: coconut
   Which scoring algorithm would you like to use?

   0 - Simple: One point per character
   1 - Vowel Bonus: Vowels are worth 3 points
   2 - Scrabble: Uses scrabble point system
   Enter 0, 1, or 2: 0
   Score for 'coconut': 7


C) Transform Scrabble Scoring
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Currently, the software contains the data structure below for the traditional
Scrabble scoring algorithm. Take a few moments to review how the
``OLD_POINT_STRUCTURE`` dictionary relates a point value to a letter.

.. sourcecode:: python
   :linenos:

   OLD_POINT_STRUCTURE = {
      1: ['A', 'E', 'I', 'O', 'U', 'L', 'N', 'R', 'S', 'T'],
      2: ['D', 'G'],
      3: ['B', 'C', 'M', 'P'],
      4: ['F', 'H', 'V', 'W', 'Y'],
      5: ['K'],
      8: ['J', 'X'],
      10: ['Q', 'Z']
   }

The *keys* of ``OLD_POINT_STRUCTURE`` are the Scrabble points, and the
*values* are lists of letters. All letters in the list have the Scrabble
point value equal to the key. For example, ``'A'`` and ``'R'`` are worth 1,
``'K'`` is worth 5, and ``'J'`` is worth 8.

To find the point value for a letter with the old format, the program must
iterate over each key in ``OLD_POINT_STRUCTURE`` and then check if the letter is
inside the list paired with that key. *This search within a search is
inefficient*.

.. admonition:: Tip

   Think about this for a second. The scoring action takes in letters in a word as input
   and outputs numerical point values. 

   We can improve our program by rewriting the data structure to better fit the action
   we want to take. Keep this idea in mind as you go on to code your own
   applications.

It would improve the performance of the program to create a ``new_point_structure`` object that has 26 keys,
one for each letter. The value of each key will be the Scrabble point value.

Examples of the new key storage:

* ``a`` is worth ``1``
* ``b`` is worth ``3``
* ``c`` is worth ``3``
* ``j`` is worth ``8``

In ``new_point_structure``, the letters themselves are keys, so a *single* search
will identify a point value. 

.. admonition:: Example

   Example of ``new_point_structure`` object usage.

   .. sourcecode:: python

      print("Scrabble scoring values for");
      print("letter a: ", new_point_structure["a"]);
      print("letter j: ", new_point_structure["j"]);
      print("letter z: ", new_point_structure["z"]);

   **Output**

   ::

      Scrabble scoring values for
      letter a:  1
      letter j:  8
      letter z:  10

Transform the Object
~~~~~~~~~~~~~~~~~~~~

#. Write the rest of the ``transform()`` function. It will need to take a dictionary object 
   as a parameter - specifically the ``OLD_POINT_STRUCTURE`` object. Calling
   ``transform(OLD_POINT_STRUCTURE)`` will return a dictionary with *lowercase*
   letters as keys. The value for each key will be the points assigned to that
   letter.

   .. admonition:: Tips

      a. Recall that ``for...in`` loops iterate over the keys within a dictionary.
      b. If you need a reminder of how to assign new key/value pairs, review the
         relevant section in the ``Objects`` chapter.
      c. To access the letter lists within ``OLD_POINT_STRUCTURE``, use bracket
         notation (``OLD_POINT_STRUCTURE[key]``).
      d. To access a particular element within a letter list, add a second set of
         brackets (``OLD_POINT_STRUCTURE[key][index]``), or assign the list to a
         variable and use ``variableName[index]``.

         .. admonition:: Examples

            .. sourcecode:: Python
               :linenos:

               print("Letters with score '4':", OLD_POINT_STRUCTURE[4]);
               print("3rd letter within the key '4' list:", OLD_POINT_STRUCTURE[4][2]);

               letters = OLD_POINT_STRUCTURE[8];
               print("Letters with score '8':", letters);
               print("2nd letter within the key '8' list:", letters[1]);

            **Output**

            ::

               Letters with score '4': [ 'F', 'H', 'V', 'W', 'Y' ]
               3rd letter within the key '4' list: V

               Letters with score '8': [ 'J', 'X' ]
               2nd letter within the key '8' list: X


#. Create a new variable called ``new_point_structure`` underneath your ``transform()`` function. 
   Assign the value of ``new_point_structure`` to be the result ``transform(OLD_POINT_STRUCTURE)``.


   .. admonition:: Warning 

      Hard-coding the ``new_point_structure`` like this:

      .. sourcecode:: python

         new_point_structure = 
         {
            "a":1,
            "b": 1,
            "c": 1,
            etc ...
         }

      won't pass. And you'll lose an opportunity to practice this skill.

#. Once you've defined ``new_point_structure``, use it to finish writing the ``scrabble_scorer()`` function and then replace 
   the ``old_scrabble_scorer()`` function in ``scoring_algorithms`` with this new function.

   .. admonition:: Tip

      ``old_scrabble_scorer()`` uses ``OLD_POINT_STRUCTURE`` and returns a score for each letter in a word. You'll want to write
      ``scrabble_scorer()`` to use ``new_point_structure`` and return a cumulative score for the whole word entered.

Test Words
~~~~~~~~~~

Here are some words you can use to test your code:

#. ``Python`` = 14 points using Scrabble, 6 using Simple Score, and 8
   using Bonus Vowels.
#. ``Scrabble`` = 14 points using Scrabble, 8 using Simple Score, and 12 using
   Bonus Vowels.
#. ``Zox`` = 19 points using Scrabble, 3 using Simple Score, and 5 using Bonus
   Vowels.

.. _example-output:

Example Output
~~~~~~~~~~~~~~

::

   Let's play some Scrabble!

   Enter a word to score: rum
   Which scoring algorithm would you like to use?

   0 - Simple: One point per character
   1 - Vowel Bonus: Vowels are worth 3 points
   2 - Scrabble: Uses scrabble point system
   Enter 0, 1, or 2: 2
   Score for 'rum': 5


Bonus Missions
--------------

#. Currently, the prompts accept ANY input values. The user could enter
   something *other* than 0, 1, or 2 when selecting the scoring algorithm, and
   they could enter numbers or symbols when asked for a word. Modify your code
   to reject invalid inputs and then re-prompt the user for the correct
   information.
#. Score words spelled with blank tiles by adding ``' '`` to the
   ``new_point_structure`` dictionary. The point value for a blank tile is ``0``.


