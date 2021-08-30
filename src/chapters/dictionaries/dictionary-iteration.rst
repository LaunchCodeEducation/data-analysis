.. _dictionary-iteration:

Iterating Through Dictionaries
==============================

Many times in this book, we looped through the characters in a string or the
elements in a list without using the index values.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      my_string = 'Rutabagas!'
      numbers = [33, -25, 3.14, 86, 1168, 42, 6.022e23]

      for character in my_string:
         print(character)
      
      total = 0
      for number in numbers:
         total += number*2

Each time the loop body repeats, the loop variable (``character`` or
``number``) gets assigned the next value in the collection.

We can do something similar with dictionaries.

Loop by Keys or Values
----------------------

To loop through a dictionary, we need to specify whether to assign the loop
variable the keys or the values from the collection. To do this, we use the
``keys()`` or ``values()`` method in the ``for`` statement:

.. sourcecode:: python
   :linenos:

   for key in dictionary_name.keys():
      # Loop body...

   for value in dictionary_name.values():
      # Loop body...

In the first ``for`` loop, each time the code repeats, the loop variable
``key`` gets assigned one of the key names from the dictionary. In the second
loop, the variable ``value`` gets assigned a new value each iteration.

.. admonition:: Note

   We do not have to use the name ``key`` or ``value`` for the loop variable,
   but doing so helps keep our code clear.

.. admonition:: Try It!

   Run the following program to see how iterating through a dictionary works.

   .. replit:: python
      :slug: DictionaryIteration01
      :linenos:

      comics = {
         'Gary Larson' : 'The Far Side',
         'Terri Libenson' : 'Pajama Diaries',
         'Hilary B. Price' : 'Rhymes with Orange',
         'Jim Toomey' : "Sherman's Lagoon"
      }

      # Iterate by keys.
      print("Here are the keys from the comics dictionary:")
      for key in comics.keys():
         print(key)

      # Iterate by values.
      print("\nHere are the values from the comics dictionary:")
      for value in comics.values():
         print(value)

      # Access both keys and values.
      print("\nHere are the key/value pairs from the comics dictionary:")
      for key in comics.keys():
         print(f"Key: {key}, Value: {comics[key]}")

      # Change the dictionary values.
      print("\nUse a loop to change all of the values:")
      for key in comics.keys():
         comics[key] = comics[key].upper()

      print(comics)

   Try adding or removing key/value pairs to change the output.

Note that on lines 21 and 26, we access each value in the dictionary by using
bracket notation and the loop variable ``key``. Each iteration, ``key``
represents a new label from ``comics``, so ``comics[key]`` accesses a different
value each time the loop repeats.

.. admonition:: Try It!

   What happens if we forget to attach the ``keys()`` or ``values()`` method in
   the ``for`` statement?  Let's find out!

   Run the following program to see how Python deals with a missing method.

   .. replit:: python
      :slug: DictionaryIteration02
      :linenos:

      comics = {
         'Gary Larson' : 'The Far Side',
         'Terri Libenson' : 'Pajama Diaries',
         'Hilary B. Price' : 'Rhymes with Orange',
         'Jim Toomey' : "Sherman's Lagoon"
      }

      # What gets printed if we don't attach .keys() or .values() to comics?
      for data in comics:
         print(data)

Aha! By default, Python iterates through a dictionary by using the key names.

.. _key-value-iteration:

Loop by Key/Value Pairs
^^^^^^^^^^^^^^^^^^^^^^^

The ``items()`` method returns each key/value pair as a unit, and it allows us
to assign BOTH the key and value from the dictionary to separate variables. The
general syntax for this is:

.. sourcecode:: python

   for (key, value) in dictionary_name.items():

In the ``for`` statement, we define a pair of variables ``(key, value)`` to
hold a key name and its linked value from the dictionary. Each iteration, these
two variables represent a new key/value pair from the collection.

.. admonition:: Example

   Compare the following two loops, which do exactly the same thing:

   .. sourcecode:: python
      :linenos:

      comics = {
         'Gary Larson' : 'The Far Side',
         'Terri Libenson' : 'Pajama Diaries',
         'Hilary B. Price' : 'Rhymes with Orange',
         'Jim Toomey' : "Sherman's Lagoon"
      }

      # Iterate by keys, and print out the dictionary key/value pairs:
      for key in comics.keys():
         print(key, comics[key])

      # Iterate by key/value pairs:
      for (key, value) in comics.items():
         print(key, value)

   By defining a pair of variables, we can access the values from the
   dictionary without needing to use bracket notation. On line 14, the variable
   ``value`` replaces ``comics[key]`` in our code. 

Sorting by Keys
---------------

Dictionaries are *unordered* collections, so they do NOT include any type of
sorting method. However, sometimes we might want to access or display the
key/value pairs in a particular order---like alphabetically by key name.

If we want to sort a dictionary, the short answer is...we can't. However, we
can use a work-around. We won't change the order of the key/value pairs in the
dictionary. Instead, we will use a list, which can be sorted.

.. admonition:: Try It!

   Let's see how to print out the key/value pairs in a dictionary
   alphabetically by key name.

   #. Run the program as-is. Notice that the loop prints the key/value pairs in
      the order they occur in the collection.
   #. On line 13, add the statement ``keys_list = list(grocery_bill.keys())``.
      On line 14, print ``keys_list`` and run the program to see the result.

      - Line 13 does NOT change the dictionary. Instead, the ``list()``
        function creates a new list that contains copies of all the key names
        from ``grocery_bill``.
   
   #. On line 14, replace the ``print`` statement with ``keys_list.sort()``,
      which alphabetizes the strings in the list.

      - Note that line 14 sorts the *list* and NOT the dictionary!

   #. Change the ``for`` statement to loop through ``keys_list`` instead of
      ``grocery_bill.keys()``. Run the program again so see the alphabetical
      result.
   
   .. replit:: python
      :slug: DictionaryIteration03
      :linenos:

      #!/bin/python3
      grocery_bill = {
         'bananas' : 1.77,
         'pears' : 6.97,
         'broccoli' : 1.98,
         'cheese' : 5.99,
         'soy milk' : 6.99,
         'orange juice' : 5.49,
         'eggs' : 1.98,
         'carrots' : 2.99
      }

      for key in grocery_bill.keys():
         print("{0}: {1}".format(key, grocery_bill[key]))


   Note that we do not need to change the final ``print`` statement. It still
   uses the loop variable ``key``, but in this case it takes elements from the
   list we created in line 13 and sorted in line 14.

   ``grocery_bill[key]`` still refers to a value from the dictionary, but now
   we access the values in a different (sorted) order!

   If we print the ``grocery_bill`` dictionary at the end of the program, we
   can prove that we did NOT alter the order of the key/value paris.

By adding copies of the key names to a separate list, we can sort the list to
get the order we want. Then we use the key names *from the sorted list* to
access the values in the dictionary.

Check Your Understanding
------------------------

.. admonition:: Question

   Given the code:

   .. sourcecode:: python
      :linenos:

      comics = {
         'Georgia Dunn' : 'Breaking Cat News',
         'Jan Eliot' : 'Stone Soup',
         'Wiley Miller' : 'Non Sequitur',         
         'Bill Watterson' : 'Calvin and Hobbs'
      }

      for key in comics.keys():
         print(key, comics[key])

   What is the value of ``comics[key]`` the *third* time through the loop?

   a. ``'Wiley Miller'``
   b. ``'Bill Watterson'``
   c. ``'Non Sequitur'``
   d. ``'Calvin and Hobbs'``

.. Answer = c


