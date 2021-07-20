Search a Dictionary
===================

With both lists and strings, we used the ``in`` and ``not in`` operators to
search for specific values. These expressions returned either ``True`` or
``False`` depending on if the value was found in the collection.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      greeting = 'Hello, World!'
      fruits = ['apple', 'banana', 'pear', 'kiwi', 'orange']
      numbers = [28, 32, 7, 29, 33, 0]

      print('or' in greeting)  # Search for the substring 'or' in the larger string.
      print('nana' in fruits)  # Search for the value 'nana' in the list of strings.

      print('!' not in greeting) # Check if '!' is NOT in 'Hello, World!'.
      print(42 not in numbers)   # Check if 42 is NOT in the numbers list.

   **Console Output**

   ::

      True
      False
      False
      True

Since the elements in a dictionary come as pairs, we search for an item in
*either* the set of keys *or* the set of values.

We practiced with the ``keys()`` and ``values()`` methods in the previous two
sections, and we can use them in a similar way to search a dictionary.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      ticket_holders = {
         'Bob' : 100,
         'Jessi' : 103,
         'Maria' : 101,
         'Devon' : 102
      }

      print(101 in ticket_holders.keys())
      print(101 in ticket_holders.values())

      print('Jessi' in ticket_holders.keys())
      print('Jessi' in ticket_holders.values())

   **Console Output**

   ::

      False
      True
      True
      False

   #. In line 8, ``101 in ticket_holders.keys()`` returns ``False``. Even
      though ``101`` is in the dictionary, it is a *value*, and in this case we
      are searching through the *keys*.
   #. In line 9, ``101 in ticket_holders.values()`` returns ``True``.
   #. In lines 11 and 12, we search for the string ``'Jessi'`` first in the
      keys and then in the values.

Default Search Method
---------------------

If we do not add the ``keys()`` or ``values()`` method after the dictionary
name, Python searches the *keys* by default.

This means that

.. sourcecode:: python

   search_value in dictionary_name.keys()

returns the same result as

.. sourcecode:: python

   search_value in dictionary_name

Try It!
-------

Let's build a quick search algorithm for a ``phone_book`` dictionary. In the
code editor below, begin with the following:

#. Note how the input statement on line 12 modifies the name entered by the
   user. Attaching the ``lower()`` and ``capitalize()`` methods makes sure that
   the string matches the format of the keys in ``phone_book``. The entries
   ``'john', 'John', and 'JOHN'`` all get converted to ``'John'``.
#. On lines 15-18, add an ``if/else`` block that does the following:

   a. Checks if ``name`` is one of the keys in ``phone_book``.
   b. If ``True``, print ``"The number for ___ is ___."`` Fill in the first
      blank with the entered name (the key). Fill in the second blank with that
      person's phone number (the value).
   c. If ``False``, print ``"Sorry, ___ is not in your phone book."`` Fill in
      the blank with the entered name.

#. Run the program several times to make sure it responds correctly.

.. replit:: python
   :slug: DictionarySearch
   :linenos:

   phone_book = {
      'Abby': '555-5081', 
      'Mike': '555-5515', 
      'Daniel': '555-5037', 
      'Kimberly': '555-5509', 
      'Jt': '555-5198',
      'Becky' : '555-5162',
      'Gordon' : '555-5299',
      'James' : '555-5837'
   }

   name = input("Enter a name: ").lower().capitalize()

   # Code the first if/else block here:


**Now expand the program:**

#. On line 20, paste a new input statement:

   .. sourcecode:: python

      ph_number = input("Enter a phone number: ")

#. Add a second ``if/else`` block that:

   a. Checks if ``ph_number`` is NOT a value in the ``phone_book``.
   b. If ``True``, prints ``"___ is not in your phone book!"``. Fill in the
      blank with the entered phone number.
   c. If ``False``, runs the following loop. Be sure to indent it properly
      compared to the ``else`` keyword.

      .. sourcecode:: python
         :lineno-start: 26

         for (key, value) in phone_book.items():
            if value == ph_number:
               print(f"Dialing {ph_number} will call {key}.")

Sample Output
^^^^^^^^^^^^^

Properly done, your output should look something like this:

::

   Enter a name:  kimberly
   The number for Kimberly is 555-5509.
   Enter a phone number:  333-3333
   333-3333 is not in your phone book!

:: 

   Enter a name:  will
   Sorry, Will is not in your phone book.
   Enter a phone number:  555-5162
   Dialing 555-5162 will call Becky.

Bonus!
^^^^^^

Update the program to add a new key/value pair to the dictionary if the name
entered by the user is NOT already in ``phone_book``.
