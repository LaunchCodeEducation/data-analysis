Special Characters
==================

.. index::
   single: character; special
   single: newline
   single: tab

Aside from letters, numbers, and symbols, there is another class of characters
we can use in strings, known as **special characters**. These characters
involve special codes that all begin with a ``\`` (backslash). Special
characters allow us to include control characters, whitespace characters, and
items that do not appear on our keyboards (like shapes or emojis).

Newline and Tab
---------------

Two commonly used special characters are ``\n`` and ``\t``, which are the
newline and tab characters, respectively. A **newline** represents tapping the
*Return* or *Enter* key while typing.

.. admonition:: Example

   .. sourcecode:: python

      print("A message,\nbroken across lines,\n\tand indented.")

   **Console Output**

   ::

      A message,
      broken across lines,
         and indented.

.. admonition:: Try It!

   Modify the code in Replit below to produce this output:

   ::

      Use newline
         and tab
            characters to
               create this
            output with
         a single
      print statement.


   .. replit:: python
      :slug: SpecialCharacterPractice
      :linenos:

      # Use the special characters for newline and tab to produce the indented, multi-line output shown in the instructions.

      print('Use newline and tab characters to create this output with a single print statement.')

.. _unicode:

Other Characters
----------------

.. index:: ! Unicode

We can also add characters to a string that do not appear on all keyboards.
These **Unicode characters** use combinations of the form ``\uXXXX``, where the
four Xs are numbers or letters that stand for a particular symbol. This allows
us to use character sets that don't use the Latin letters (A-Z), such as Greek,
Cyrillic, and Arabic, as well as a wide array of non-letter symbols.

.. admonition:: Example

   .. sourcecode:: python

      print('\u25E8     \u26BD     \u26A1')

   **Console Output**

   ::

      ◨     ⚽     ⚡

For a complete listing of codes, check out this
`Unicode table <https://unicode-table.com/en/>`__.

Check Your Understanding
------------------------

.. admonition:: Question

   Which of the options below prints ``'Special'`` and ``'characters'`` on
   separate lines?

   a. ``print('Special\ncharacters')``
   b. ``print('Special/ncharacters')``
   c. ``print('Special', 'characters')``
   d. ``print('Special\tcharacters')``
   e. ``print('Special/tcharacters')``
   
.. Answer = a


