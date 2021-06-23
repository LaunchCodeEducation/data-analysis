String Methods
==============

The ``str`` data type includes a special group of operations, called *methods*,
that we can use to make routine tasks easier. A method performs a specific
action on the data within an object. For strings, the methods usually create a
new string from the characters of the original.

Python provides many useful methods for string objects. 

Common String Methods
---------------------

.. index::
   single: string; methods

Here we present the most commonly-used string methods. Clicking on the name of
any method leads to examples and a more detailed description.

.. list-table:: Common String Methods
   :header-rows: 1

   * - Method
     - Syntax
     - Description
   * - :ref:`count <string-count-examples>`
     - ``string_name.count(search_string)``
     - Returns the number of times ``search_string`` occurs in ``string_name``.
   * - :ref:`find <string-find-examples>`
     - ``string_name.find(a_string)``
     - Returns the index of the first occurrence of ``a_string`` in
       ``string_name``. The method returns -1 if ``a_string`` is not found.
   * - :ref:`index <string-find-examples>`
     - ``string_name.index(a_string)``
     - Returns the index of the first occurrence of ``a_string`` in
       ``string_name``. If ``a_string`` is not found, the method throws an
       error.
   * - :ref:`lower <string-lower-examples>`
     - ``string_name.lower()``
     - Returns a copy of the given string, with all uppercase letters converted
       to lowercase.
   * - :ref:`replace <string-replace-examples>`
     - ``string_name.replace(a_string, replacement)``
     - Returns a copy of ``string_name`` with every occurrence of ``a_string``
       replaced by the ``replacement`` string.
   * - :ref:`split and list <string-split-examples>`
     - ``string_name.split('character')``
     - Splits the string at each occurrence of ``character``, and returns a
       list of smaller strings.
   * - :ref:`strip <string-strip-examples>`
     - ``string_name.strip('characters')``
     - Returns a copy of the given string with leading and trailing
       ``characters`` strings removed. By default, ``characters`` is a space.
   * - :ref:`upper <string-upper-examples>`
     - ``string_name.upper()``
     - Returns a copy of the given string, with all lowercase letters converted
       to uppercase.

You can find complete lists of the Python string methods on 
`W3Schools <https://www.w3schools.com/python/python_ref_string.asp>`__ and 
`the official Python documentation site <https://docs.python.org/3/library/stdtypes.html?highlight=lower#string-methods>`__.


.. admonition:: Tip

   String methods can be combined in a process called **method chaining**.
   Given ``word = 'Python'``:
   
   #. ``word.upper()`` returns ``PYTHON``.
   #. ``word.replace('n', 'n!!!')`` returns ``Python!!!``
   
   Chaining the methods together as ``word.replace('n', 'n!!!').upper()``
   returns ``PYTHON!!!``.
   
   What would ``word.lower().strip('p').find('t')`` return?

Strings Are Immutable
---------------------

As we learned, strings are *immutable*. Therefore, string methods will NOT
change the value of a string itself. Instead, they *return* a new string that
is the result of the operation.

Let's take a look at this behavior with the ``lower()`` and ``replace()``
methods.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      nonprofit = "LaunchCode"
      lowercase = nonprofit.lower()
      meal_plan = nonprofit.replace('a', '')

      print(lowercase)
      print(meal_plan)
      print(nonprofit)

   **Console Output**

   ::

      launchcode
      LunchCode
      LaunchCode

Note the following:

#. In line 2, ``nonprofit.lower()`` evaluates to ``"launchcode"`` and assigns
   that string to the variable ``lowercase``.
#. In line 3, ``nonprofit.replace('a', '')`` removes the letter ``'a'`` and assigns
   a new string to ``meal_plan``.
#. Despite the actions in lines 2 and 3, the value of ``nonprofit`` stays the
   same.

This will be true for EVERY string method. Each method creates a *brand new
string*, which we can print to the screen or assign to a variable. The
original string never changes.

Check Your Understanding
------------------------

Follow the links in the table above for the ``replace``  and ``strip`` methods.
Review the content and then answer the following questions.

.. admonition:: Question

   What is printed by the following code?

   .. sourcecode:: python
      :linenos:

      text = "Python rocks!"
      text.replace('o', 'q')
      text.strip('!P')
      print(text)
   
   a. Pythqn rocks
   b. ythqn rqcks
   c. ythqn rqcks!
   d. Python rocks!

.. Answer: d

.. admonition:: Question

   What is the value of the string printed by the following program?

   .. sourcecode:: python
      :linenos:

      org = "  The LaunchCode Foundation "
      trimmed = org.strip()

      print(trimmed)

   a. ``"  The LaunchCode Foundation "``
   b. ``"The LaunchCode Foundation"``
   c. ``"TheLaunchCodeFoundation"``
   d. ``" The LaunchCode Foundation"``

.. Answer: b

.. admonition:: Question

   Given ``word = "Rutabaga"``, what is the value returned by
   ``word.lower().strip('r').find('t')``?

   a. ``'utabaga'``
   b. ``2``
   c. ``1``
   d. ``'t'``

.. Answer: c

