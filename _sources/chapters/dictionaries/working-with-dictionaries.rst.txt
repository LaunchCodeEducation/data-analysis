Working with Dictionaries
=========================

Dictionaries are *mutable*, so we can change the value assigned to a key, add
new key/value pairs, or remove key/value pairs.

Since dictionaries are *unordered*, we have no options for sorting or
rearranging the key/value pairs within the collections.

Change One Value
----------------

To update a single value in a dictionary, use the syntax:

.. sourcecode:: python

   dictionary_name[key] = new_value

``dictionary_name[key]`` identifies the value in the collection that we want to
change. The ``=`` operator assigns ``new_value`` to that key.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      phone_book = {
         'Mom' : '555-5555',
         'Work' : '555-5556',
         'Home' : '123-456-7890'
      }
      print(phone_book)

      phone_book['Work'] = '314-555-5556'  # Link the key 'Work' to the value '314-555-5556'.
      print(phone_book)

   **Console Output**

   ::

      {'Mom' : '555-5555', 'Work' : '555-5556', 'Home' : '123-456-7890'}
      {'Mom' : '555-5555', 'Work' : '314-555-5556', 'Home' : '123-456-7890'}

.. admonition:: Note

   We cannot use this method to change the names of the keys.

Add a New Key/Value Pair
------------------------

After defining a dictionary, we can add new new key/value pairs at any time by
using bracket syntax:

.. sourcecode:: python

   dictionary_name['new_key'] = new_value

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      phone_book = {
         'Mom' : '555-5555',
         'Work' : '555-5556',
         'Home' : '123-456-7890'
      }
      print(phone_book)

      phone_book['BFF'] = '555-5557'
      print(phone_book)
   
   **Console Output**

   ::

      {'Mom' : '555-5555', 'Work' : '555-5556', 'Home' : '123-456-7890'}
      {'Mom' : '555-5555', 'Work' : '555-5556', 'Home' : '123-456-7890', 'BFF' : '555-5557'}

Remove a Key/Value Pair
-----------------------

To remove a key/value pair from a dictionary, use the ``del`` keyword. The
general syntax is:

.. sourcecode:: python

   del dictionary_name[key]

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      phone_book = {
         'Mom' : '555-5555',
         'Work' : '555-5556',
         'Home' : '123-456-7890',
         'BFF' : '555-5557'
      }
      print(phone_book)

      del phone_book['Home']
      print(phone_book)
   
   **Console Output**

   ::

      {'Mom' : '555-5555', 'Work' : '555-5556', 'Home' : '123-456-7890', 'BFF' : '555-5557'}
      {'Mom' : '555-5555', 'Work' : '555-5556', 'BFF' : '555-5557'}

.. admonition:: Note

   Once we define a key, it remains in the dictionary unless we use ``del`` to
   remove it.

   For example, if we wanted to rename the key ``'Mom'`` to ``'Mother'``, we
   would have to delete the old key first, then add a new key/value pair.

   .. sourcecode:: python
      :lineno-start: 9

      del phone_book['Mom']
      phone_book['Mother'] = '555-5555'

Try It!
-------

.. admonition:: Example

   Use a dictionary to keep track of favorite ice cream flavors!

   In the editor below:

   #. Change the value for ``'Mom'`` to something more exciting than
      ``'vanilla'``.
   #. Add your own name and favorite flavor to the dictionary.
   #. Use ``del`` to remove the ``'Odd choice'`` key/value pair.
   #. Fix the misspelling in the ``'teachher'`` key.
   
   .. replit:: python
      :slug: DictionaryOperations
      :linenos:

      favorite_ic_flavors = {
         'Mom' : 'vanilla',
         'Jerry' : 'Cherry Garcia',
         'Ben' : 'Chocolate Fudge Brownie',
         'Jenny' : 'Mint Chocolate Chip',
         'Odd choice' : 'pickled mango',
         'teachher' : 'Rocky Road'
      }

      print(favorite_ic_flavors)

Check Your Understanding
------------------------

.. admonition:: Question

   Given the following dictionary:

   .. sourcecode:: python

      pet_population = {'cats' : 10, 'dogs' : 5, 'elephants' : 25}
   
   What value does ``len(pet_population)`` return?

   a. 3
   b. 6
   c. 40

.. Answer = a

.. admonition:: Question

   Using the same ``pet_population`` dictionary, what would the following
   statement do?

   .. sourcecode:: python

      pet_population['birds'] = 5

   a. Throw an error message because ``pet_population`` does not contain a ``'birds'`` key.
   b. Add the ``'birds' : 5`` key/value pair to the dictionary.
   c. Add five ``'birds'`` keys to the dictionary.
   d. Replace the ``'dogs'`` key with ``'birds'``.

.. Answer = b

.. admonition:: Question

   What is printed by the following statements?

   .. sourcecode:: python
      :linenos:

      pet_population = {'cats' : 10, 'dogs' : 5, 'elephants' : 25}

      pet_population['mice'] = pet_population['cats'] + pet_population['dogs']

      print(pet_population['mice'])

   a. 0
   b. 5
   c. 10
   d. 15

.. Answer = d

.. admonition:: Question

   Once we added mice to our pet collection, all the elephants ran away! Which
   of the following shows the correct syntax for setting the value of the
   ``'elephants'`` key to zero?

   a. ``pet_population['elephants'] = 0``
   b. ``pet_population['elephants'] = ''``
   c. ``del pet_population['elephants']``
   d. ``pet_population[2] = 0``

.. Answer = a


