.. _keys-values-items-examples:

Return Keys, Values, or Key/Value Pairs
=======================================

The structure of a Python dictionary involves *pairs* of items. Each element in
the collection contains a key and a value.

Python provides two methods that allow us to access all of the keys (without
their values), or all of the values (without their keys).

.. _dictionary-keys:

Return All Keys
---------------

.. index::
   single: dictionary; keys()

The general syntax for the ``keys()`` method is:

.. sourcecode:: Python

   dictionary_name.keys()

No arguments are needed inside the parentheses, and the method returns an
*object* that contains all of the keys in the dictionary.

Let's explore what this means.

.. admonition:: Example

   Print the *object* returned by the ``keys()`` method:

   .. sourcecode:: Python
      :linenos:

      phone_book = {
         'Mom' : '555-5555',
         'Work' : '555-5556',
         'Home' : '123-456-7890',
         'BFF' : '555-5557'
      }

      book_keys = phone_book.keys()
      print(book_keys)
      print(type(book_keys))

   **Console Output**

   ::

      dict_keys(['Mom', 'Work', 'Home', 'BFF'])
      <class 'dict_keys'>

Notice that when we print ``book_keys``, we see something that looks like a
list, but that list is enclosed in ``dict_keys()``. Line 10 shows us that
``book_keys`` is a data type that we have not seen before---``dict_keys``.

Good news! We do not need a deep understanding of the ``dict_keys`` data type.
We just need to know how to use it. One option is to use the ``list()``
function to convert the ``dict_keys`` object into a list.

.. admonition:: Example

   .. sourcecode:: Python
      :lineno-start: 8

      book_keys = list(phone_book.keys())
      print(book_keys)
      print(type(book_keys))
      print(book_keys[0])
   
   **Console Output**

   ::

      ['Mom', 'Work', 'Home', 'BFF']
      <class 'list'>
      Mom

In the :ref:`dictionary iteration <dictionary-iteration>` section, we see how
to apply the ``keys()`` method to loop through a dictionary.

.. _dictionary-values:

Return All Values
-----------------

.. index::
   single: dictionary; values()

The general syntax for the ``values()`` method is:

.. sourcecode:: Python

   dictionary_name.values()

No arguments are needed inside the parentheses, and the method returns an
*object* that contains all of the values from the dictionary.

.. admonition:: Example

   .. sourcecode:: Python
      :linenos:

      phone_book = {
         'Mom' : '555-5555',
         'Work' : '555-5556',
         'Home' : '123-456-7890',
         'BFF' : '555-5557'
      }

      book_values = phone_book.values()
      print(book_values)
      print(type(book_values))
      print(list(book_values))

   **Console Output**

   ::

      dict_values(['555-5555', '555-5556', '123-456-7890', '555-5557'])
      <class 'dict_values'>
      ['555-5555', '555-5556', '123-456-7890', '555-5557']

By collecting all of the values from a dictionary into one object, we can
loop through the entries or search the object for a specific value.

.. _dictionary-items:

Return All Key/Value Pairs
--------------------------

.. index::
   single: dictionary; items()

The general syntax for the ``items()`` method is:

.. sourcecode:: Python

   dictionary_name.items()

No arguments are needed inside the parentheses, and the method returns an
*object* that contains all of the key/value pairs from the dictionary.

Just like with ``keys()`` and ``values()``, we can convert the *object* into
a list.

.. admonition:: Example

   .. sourcecode:: Python
      :linenos:

      phone_book = {
         'Mom' : '555-5555',
         'Work' : '555-5556',
         'Home' : '123-456-7890',
         'BFF' : '555-5557'
      }

      book_items = list(phone_book.items())
      print(book_items)
      print(book_items[0])
      print(book_items[0][0], book_items[0][1])

   **Console Output**

   ::

      [('Mom', '555-5555'), ('Work', '555-5556'), ('Home', '123-456-7890'), ('BFF', '555-5557')]
      ('Mom', '555-5555')
      Mom 555-5555

Note that each element in the list comes is a *pair*, which can be accessed
with bracket notation. A single bracket, like ``book_items[0]``, accesses one
pair in the list. A pair of brackets, like ``book_items[1][0]`` lets us access
one half of a pair.

Why?
----

When we define the ``keys(), values()``, and ``items()`` methods on their own,
it might be difficult to see why they are so important. This is especially true
when we throw in the *returns an object* business.

To fully understand why these dictionary methods are helpful, we must use them
in concrete examples. If you haven't done so, read the
:ref:`dictionary iteration <dictionary-iteration>` section and then return to
this appendix page.
