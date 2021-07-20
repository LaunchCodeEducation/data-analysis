Dictionary Methods
==================

.. index::
   single: list; methods

As with strings and lists, Python provides us with some useful **methods** for
dictionaries. These methods will either *change* an existing dictionary,
*return* information about the dictionary, or *create and return* a new
dictionary.

.. _dictionary-methods:

Common Dictionary Methods
-------------------------

Here is a sample of the most frequently used dictionary methods. A more
complete list can be found at
`W3Schools <https://www.w3schools.com/python/python_ref_dictionary.asp>`__.

To see detailed examples for a particular method, click on its name.

.. list-table:: Common Dictionary Methods
   :header-rows: 1

   * - Method
     - Syntax
     - Description
   * - :ref:`clear <dictionary-clear>`
     - ``dictionary_name.clear()``
     - Removes all key/value pairs from a dictionary.
   * - :ref:`copy <dictionary-copy-example>`
     - ``dictionary_name.copy()``
     - Returns an independent copy of a dictionary. This is also called
       *cloning*.
   * - :ref:`pop <dictionary-pop>`
     - ``dictionary_name.pop(key)``
     - Removes the selected key/value pair from the dictionary and returns the
       value.
   * - :ref:`keys <dictionary-keys>`
     - ``dictionary_name.keys()``
     - Returns all of the key names in the dictionary, which can then be
       moved into a list.
   * - :ref:`values <dictionary-values>`
     - ``dictionary_name.values()``
     - Returns all of the values in the dictionary, which can then be
       moved into a list.
   * - :ref:`items <dictionary-items>`
     - ``dictionary_name.items()``
     - Returns all of the key/value pairs in the dictionary, which can then be
       moved into a list.

.. admonition:: Note

   Since dictionaries are unordered, we have no need for methods that sort the
   key/value pairs.

``max``, ``min``, and ``len``
-----------------------------

Just like with strings and lists, the ``len()`` function returns the number of
items in a dictionary. Note that each key/value pair gets counted as a single
item.

.. admonition:: Try It!

   #. Run the code as-is first to see the results.
   #. Add characters to the ``text`` string, elements to the ``words`` list,
      and new key/value pairs to ``state_capitals``.
   #. Run the code again to see how ``len()`` counts the entries for each
      collection.

   .. replit:: python
      :slug: DictionaryMethods01
      :linenos:

      text = "What does the fox say?"
         words = ['What', 'does', 'the', 'fox', 'say?']
         state_capitals = {
         'MO' : 'Jefferson City',
         'CA' : 'Sacramento',
         'TX' : 'Austin',
         'HI' : 'Honolulu'
      }

      print(len(text))
      print(len(words))
      print(len(state_capitals))

``max()`` and ``min()`` provide similar results for dictionaries as they do for
strings and lists. By default, the functions return the largest or smallest KEY
in the dictionary, not value. As a best practice, we should specify if we are
looking for a largest/smallest key or value.

.. sourcecode:: python
   :linenos:

   max(dictionary_name.keys())    # Returns the largest key from the dictionary.
   min(dictionary_name.values())  # Returns the smallest value in the dictionary.

   min(dictionary_name)           # Returns the smallest key from the dictionary.

.. admonition:: Note

   Remember that for strings, ``max()`` and ``min()`` return values based on
   their position in the alphabet, with capital letters coming before
   lowercase.

   Using this model, Python considers ``"Zebra"`` larger than ``"Hippo"`` but
   smaller than ``"apple"``.

.. admonition:: Try It!

   #. Print the maximum and minimum *keys* from the ``num_animals`` dictionary.
   #. Print the maximum and minimum *values* from the dictionary.
   #. What happens if you use the ``.items()`` method instead of ``.keys()`` or
      ``.values()``?

   .. replit:: python
      :slug: DictionaryMethods02
      :linenos:

      num_animals = {
         'lions' : 3,
         'tigers' : 2,
         'bears' : 8,
         'pigeons' : 3000,
         'snakes' : 37,
         'Koalas' : 3
      }

      # Code your four print statements here:

Check Your Understanding
------------------------

As you answer these questions, follow the links given in the
:ref:`method table <dictionary-methods>` as needed.

.. admonition:: Question

   What is printed by the following statements?

   .. sourcecode:: python
      :linenos:

      num_animals = {"cats":12, "dogs":6, "elephants":23, "bears":20}

      removed = num_animals.pop('elephants')
      print(removed)

   a. elephants
   b. 23
   c. {"cats":12, "dogs":6, "bears":20}

.. Answer = b

.. admonition:: Question

   What is printed by the following statements?

   .. sourcecode:: python
      :linenos:

      num_animals = {"cats":12, "dogs":6, "elephants":23, "bears":20}

      print(min(num_animals))

   a. bears
   b. dogs
   c. 6
   d. 20

.. Answer = a

.. admonition:: Question

   What is printed by the following statements?

   .. sourcecode:: python
      :linenos:

      num_animals = {"cats":12, "dogs":6, "elephants":23, "bears":20}

      key_list = list(num_animals.keys())
      key_list.sort()
      
      print(key_list[3])

   a. cats
   b. dogs
   c. elephants
   d. bears

.. Answer = c


   
