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

   Modify the code in the editor below to produce this output:

   ::

      Use newline
         and tab
            characters to
               create this
            output with
         a single
      print statement.


   .. raw:: html

      <iframe height="400px" width="100%" src="https://repl.it/@launchcode/LCHS-Special-Character-Practice?lite=true" scrolling="no" frameborder="yes" allowtransparency="true"></iframe>

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

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, true)"> <span style="color:#419f6a; font-weight: bold">print('Special\ncharacters')</span></li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">print('Special/ncharacters')</span></li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">print('Special', 'characters')</span></li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">print('Special\tcharacters')</span></li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">print('Special/tcharacters')</span></li>
      </ol>
      <p id="Q1"></p>
   
.. Answer = a


