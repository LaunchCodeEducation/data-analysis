Data Type for ``True``/``False``
================================

In order for us to build code that can make decisions, we need to understand
how programming languages represent *true* and *false*.

.. admonition:: Example

   If we run the following code, we would see in the following output.

   .. sourcecode:: Python
      :linenos:

      print('dog' == 'cat')
      print(3 < 4)
      print(3 > 10)
      print('dog' != 'cat')

   **Console Output**

   ::

      False
      True
      False
      True


In the code above, we make four *comparisons* and then print the results to the
console. Python evaluates each comparison as being either ``True`` or
``False``.

#. In line 1, the *equality operator* ``==`` compares the strings ``'dog'``
   and ``'cat'``. Since these are NOT the same, the comparison returns the
   value ``False``.
#. In line 2, the operator ``<`` compares the values of 3 and 4. Since 3 is
   indeed less than 4, comparison returns the result ``True``.
#. The comparison in line 3 returns ``False``, since 3 is NOT larger than 10.
#. In line 4, the ``!=`` operator stands for "not equal", so
   ``'dog' != 'cat'`` returns ``True``, while something like ``3 != 3`` would
   return ``False``.

Identify ``True`` and ``False``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Recall that the ``type()`` function tells us the data type of what's inside
the ``()``.

.. sourcode:: Python
   :linenos:

   print(3 < 4)
   print(type(3 < 4))

   print('dog' == 'cat')
   print(type('dog' == 'cat'))

**Console Output**

::

   True
   <class 'bool'>
   False
   <class 'bool'>

In the previous chapter, we learned about three data types---``int``,
``float``, and ``string``. The first two deal with numbers, while ``string``
deals with collections of characters.

.. index:: ! boolean, ! bool, data type

We can now add the data type ``bool``, which stands for
**boolean value**, to our list.

Boolean Values
--------------

.. index:: ! True, ! False

There are only two boolean values---``True`` and ``False``.

.. admonition:: Note

   Capitalization matters! Since Python is case-sensitive, ``true`` and
   ``false`` are NOT valid boolean values.

The values ``True`` and ``False`` are NOT strings. We can see this by printing
another set of ``type()`` results:

.. admonition:: Example

   .. sourcecode:: Python
      :linenos:

      print(type(True))
      print(type("True"))
      print(True == "True")

   **Console Output**

   ::

      <class 'bool'>
      <class 'str'>
      False

Putting quotes around boolean values (``"True"`` and ``"False"``) makes them
strings, just like ``"1234"`` is a string rather than an ``int`` data type.

Line 3 shows that even though they look similar, ``True`` and ``"True"`` are
NOT the same! ``str`` and ``bool`` are different data types.

Data Type Review
----------------

#. The string (``str``) data type represents a collection of characters.
#. The integer (``int``) data type represents a whole number.
#. The float (``float``) data type represents a decimal value.
#. The boolean (``bool``) data type represents ``True`` or ``False``.
