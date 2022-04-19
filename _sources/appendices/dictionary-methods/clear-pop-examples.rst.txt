Removing Items From a Dictionary
================================

The ``clear`` and ``pop`` dictionary methods *mutate* (change) the original
collection.

.. index::
   single: dictionary; clear

.. _dictionary-clear:

``clear`` Example
-----------------

The general syntax for this method is:

.. sourcecode:: python

   dictionary_name.clear()

``clear`` removes all key/value pairs from a dictionary. The dictionary still
exists, but it is empty.

No arguments go inside the ``()``.

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

      phone_book.clear()
      print(phone_book)

      print(len(phone_book))  # Print the length of the dictionary

   **Output**

   ::

      {'Mom': '555-5555', 'Work': '555-5556', 'Home': '123-456-7890', 'BFF': '555-5557'}
      {}
      0

.. index::
   single: dictionary; pop

.. _dictionary-pop:

``pop`` Examples
----------------

The general syntax for this method is:

.. sourcecode:: python

   dictionary_name.pop(key)

``pop`` removes the key indicated inside the ``()``, along with its linked
value. Even though only the key goes inside the ``()``, the key/value pair gets
removed from the dictionary.

In addition to *removing* a key/value pair from the dictionary, ``pop`` also
*returns* the value. This means ``dictionary_name.pop(key)`` can be printed or
assigned to a variable.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      phone_book = {
         'Mom' : '555-5555',
         'Work' : '555-5556',
         'Home' : '123-456-7890',
         'BFF' : '555-5557'
      }

      # Remove the 'Home' key/value pair, but the returned value is lost.
      phone_book.pop('Home')
      print(phone_book)

      # Remove the 'BFF' key/value pair and assign the returned value to a variable.
      returned_value = phone_book.pop('BFF')
      print(returned_value)
      print(phone_book)

   **Output**

   ::

      {'Mom': '555-5555', 'Work': '555-5556', 'BFF': '555-5557'}
      555-5557
      {'Mom': '555-5555', 'Work': '555-5556'}

Missing Key
^^^^^^^^^^^

Unlike the :ref:`list method <list-pop-examples>` with the same name, the
``pop()`` method for dictionaries MUST include a key inside the ``()``. If we
call the method without a key, or if the key does not exist in the dictionary,
Python throws an error message.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      phone_book = {
         'Mom' : '555-5555',
         'Work' : '555-5556',
         'Home' : '123-456-7890',
         'BFF' : '555-5557'
      }

      phone_book.pop()
      phone_book.pop('Beyonce')

   #. Line 8 throws ``TypeError: pop expected at least 1 argument, got 0``.
      Python expected to find a key argument, but we did not provide one.
   #. Line 9 throws ``KeyError: 'Beyonce'``. The key ``Beyonce`` does not exist
      in ``phone_book``.

Set a Default Return Value
^^^^^^^^^^^^^^^^^^^^^^^^^^

As good coders, we can build our ``pop`` statements to only use known keys.
However, if we allow outside users to change a dictionary, then we cannot
guarantee that calling ``pop(key)`` remains safe.

Fortunately, we can set a *default* return value to avoid throwing runtime
errors! The general syntax is:

.. sourcecode:: python

   dictionary_name.pop(key, default_value)

If Python cannot find the given ``key`` inside a dictionary, it returns the
``default_value`` instead. The dictionary itself remains unchanged, but we do
avoid crashing the program.

.. admonition:: Try It!

   Run the following program several times and enter different key names. Be
   sure to try:

   #. A key that exists in ``phone_book``,
   #. A key that does NOT exist in ``phone_book``,
   #. Just hitting return to enter the empty string, ``''``.

   .. raw:: html

      <iframe src="https://trinket.io/embed/python3/56cf9e451f" width="100%" height="400" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>
