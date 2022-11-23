Accumulator Pattern with Dictionaries
=====================================

We used the :ref:`accumulator pattern <list-accumulation>` to build up from an
empty string or list, or to keep track of a running total.

Since dictionaries are just another type of collection, the accumulator pattern
works with them as well.

Adding to an Empty Dictionary
-----------------------------

We can add key/value pairs one at a time to an empty dictionary using bracket
notation:

.. admonition:: Example

   Let's create a dictionary that uses strings as key/value pairs.

   .. sourcecode:: python
      :linenos:

      eng_to_pirate = {}

      eng_to_pirate['Hello'] = 'Ahoy'
      eng_to_pirate['your'] = 'yer'
      eng_to_pirate['there'] = 'yonder'
      eng_to_pirate['element 18'] = 'Ar'

      print(eng_to_pirate)

   **Console Output**

   ::

      {'Hello': 'Ahoy', 'your': 'yer', 'there': 'yonder', 'element 18': 'Ar'}

   In lines 3 - 6, on the left hand side of the ``=`` operator we define the
   new keys for the ``eng_to_pirate`` dictionary. On the right hand side of the
   ``=``, we place the value to assign to the key.

   Each key is an English word, and its value is the related term in
   pirate-speak.

A more efficient way would be to use the accumulator pattern to add new
key/value pairs. Recall that with lists and strings, the pattern adds only one
new thing each time the loop repeats. For dictionaries, we need to add *two*
items---a new key and a new value.

Let's play with a couple of examples to practice this.

.. admonition:: Try It!

   The following program builds the ``vowel_count`` dictionary by adding a new
   key/value pair each time the loop repeats. Each character from the string
   ``'aeiou'`` becomes a key in the dictionary, which gets linked to an integer
   value.

   #. Line 5 creates an empty dictionary and assigns it to the variable
      ``vowel_counts``.
   #. Line 7 creates a new key/value pair in ``vowel_counts``. Each key is one
      character from ``vowels``, and its value is how often that letter occurs
      in the ``guide`` string.

   .. replit:: python
      :slug: DictionaryAccumulator01
      :linenos:

      guide = "Far out in the uncharted backwaters of the unfashionable end of the Western Spiral arm of the galaxy lies a small, unregarded yellow sun."
      games = "When I wake up, the other side of the bed is cold. My finger’s stretch out, seeking Prim’s warmth but finding only the rough canvas cover. She must have had bad dreams and climbed in with mother. Of course she did. This is the day of the reaping."
      vowels = 'aeiou'

      vowel_counts = {}
      for vowel in vowels:
         vowel_counts[vowel] = guide.count(vowel)

      print(vowel_counts)

   **Now try:**

   #. Indent line 9 to put the ``print`` statement inside the loop. Run the
      program to see how ``vowel_counts`` grows each time the loop repeats.
   #. Replace ``guide`` with ``games`` in line 7.
   #. Use a different string in the ``for`` statement to count different
      letters or other characters. (As a good Python coder, you should change
      your variable names once you stop counting vowels).

The previous example took the characters from the string ``'aeiou'`` and turned
them into dictionary keys. We used items from one collection (a string) to help
us build a new dictionary.

The next example combines the elements of two lists into a single dictionary.

.. admonition:: Try It!

   Let's build an English-to-pirate translation dictionary! We will use English
   words as keys and pirate words for the values.

   Feel free to add your own words to each list! However, be sure to keep both
   lists the same length.

   .. replit:: python
      :slug: DictionaryAccumulator02
      :linenos:

      english_words = ['hello', 'your', 'there', 'stop', 'yes']
      pirate_words = ['ahoy', 'yer', 'yonder', 'avast', 'aye']

      # Create an empty 'translation' dictionary.
      eng_to_pirate = {}  

      # We need to use index values to pull items from both lists.
      for index in range(len(english_words)):   
         eng_to_pirate[english_words[index]] = pirate_words[index]

      print(eng_to_pirate)
      print(eng_to_pirate['hello'].upper() + "!")

   **Note the following:**

   #. Since we pull elements from two different lists, we need to assign
      *index* values (0, 1, 2...) to the loop variable. This allows us to match
      the correct words from each list.
   #. On line 9, ``english_words[index]`` accesses one element from the
      ``english_words`` list, and it uses that element to define a new key. For
      example, the first time through the loop, the left hand side of line 9
      evaluates as:
      
      a. ``eng_to_pirate[english_words[index]]``
      b. ``eng_to_pirate[english_words[0]]``
      c. ``eng_to_pirate['hello']``

   #. The right hand side of line 9 uses the same index value, but it pulls an
      element from the ``pirate_words`` list:

      a. ``pirate_words[index]``
      b. ``pirate_words[0]``
      c. ``'ahoy'``

   #. For index value 0, line 9 reduces to ``eng_to_pirate['hello'] = 'ahoy'``,
      and this adds the ``'hello' : 'ahoy'`` key/value pair to the
      ``eng_to_pirate`` dictionary.

Accumulate with an Existing Dictionary
--------------------------------------

.. _round-function:

We can also use the accumulator pattern to perform an operation with the values
in a dictionary.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      exam_scores = {'exam_1' : 95, 'exam_2' : 90.7, 'exam_3' : 88.3}

      total = 0
      for key in exam_scores.keys():
         total += exam_scores[key]
      
      average = total / len(exam_scores)
      rounded_average = round(average, 1)
      print("The average result is {0}%.".format(rounded_average))

   **Console Output**

   ::

      The average result is 91.3%.

   **Note the following:**

   #. In line 3, we define the accumulator variable ``total`` and assign it an
      initial value of ``0``.
   #. In line 4, we set the ``for`` statement to loop through the keys of the
      ``exam_scores`` dictionary.
   #. Each time the loop repeats, line 5 increases ``total`` by the value
      linked to the current key. For example, the first time through the loop,
      line 5 operates this way:

      a. ``total += exam_scores[key]``
      b. ``total += exam_scores['exam_1']``
      c. ``total += 95``
      d. ``total = total + 95``
      e. ``total = 0 + 95``
      f. ``total = 95``
   
Check Your Understanding
------------------------

.. admonition:: Question

   What does the following program print?

   .. sourcecode:: python
      :linenos:

      my_animals = {"cats":10, "dogs":5, "elephants":25, "bears":20}
      
      total = 0
      for key in my_animals:
         if len(key) > 4:
            total += my_animals[key]

      print(total)

   a. ``0``
   b. ``25``
   c. ``45``
   d. ``60``

.. Answer = c

.. admonition:: Question

   We want to code an accumulator that takes names and ticket numbers from two
   different lists, then uses that data to add key/value pairs to a dictionary.

   The names should be the keys in the dictionary with the ticket numbers as
   their values.
   
   Given the following statements:

   .. sourcecode:: python
      :linenos:

      names = ['Bob', 'Maria', 'Devon', 'Jessi']
      ticket_numbers = [100, 101, 102, 103]
      
      ticket_holders = {}
      for index in range(len(names)):
         # Assignment statement here.

   Which of the following is the correct syntax for adding the key/value
   pairs to ``ticket_holders``?

   a. ``ticket_holders[index] = ticket_numbers[index]``
   b. ``ticket_holders[names[index]] = ticket_numbers[index]``
   c. ``ticket_holders[key] = ticket_numbers[value]``
   d. ``ticket_holders[key] = value``

.. Answer = b


