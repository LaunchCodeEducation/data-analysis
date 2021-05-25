.. _string-iteration:

Loop Through a String
=====================

The ``range`` command assigns the loop variable a new integer value each time
the loop repeats. What if we want to assign the variable something *other* than
whole numbers?

Characters Instead of Integers
------------------------------

Recall that a string is a series of characters enclosed in quotes, like
``'Hello, World!'`` or ``"Python"``. Just like ``range`` assigns a new integer
to the loop variable, we can set up a ``for`` loop to assign different
characters from a string.

Run the following program to see how this works:

.. raw:: html

   <iframe height="500px" width="100%" src="https://repl.it/@launchcode/LCHS-Loop-Through-A-String?lite=true" scrolling="no" frameborder="yes"></iframe>

Some points to notice:

#. In the ``for`` statement, a string (or a variable containing a string)
   replaces ``range``.
#. The first time the loop runs, the loop variable gets assigned the first
   character in the string (``character = 'H'`` or ``char = 'T'``).
#. Each time the loop repeats, the variable holds the next character in the
   string.
#. Unlike ``range(n)``, which does NOT assign the value of ``n`` to the loop
   variable, the last character in the string IS used.
#. Once Python reaches the end of the string, the loop ends.

Characters Another Way
----------------------

Take a look at the following code and its output:

.. admonition:: Example

   .. sourcecode:: Python
      :linenos:

      word = 'Python'

      print(word)
      print(word[0])
      print(word[1])
      print(word[5])
   
   **Console Output**

   ::

      Python
      P
      y
      n

Notice how lines 4 - 6 each print a single character from the string.
``print(word[0])`` displays only the first letter (``P``). ``word[1]`` prints
the second character, and ``word[5]`` prints the last.

.. index:: index

We will explore strings in more detail in a later chapter. For now, we just
need to recognize that every character in a string has an *index*. An index
is a number that tells us the location of a character in the string.

Like ``range``, the index values of a string start counting at ``0``.

.. figure:: figures/string-index.png
   :alt: Diagram showing the index values of a string.

   The index values of a string.

Indexes provide a different way to loop through a string:

.. admonition:: Example

   .. raw:: html

      <iframe height="450px" width="100%" src="https://repl.it/@launchcode/LCHS-Loop-Through-String-Indexes?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true"></iframe>

   Some items to note:

   #. By using ``range(6)``, the ``index`` variable takes values from 0 - 5.
   #. ``word[index]`` refers to the character in the string at position ``index``.
   #. As written, the loop only displays characters up to index 5.
      
      - Try replacing the string with a longer one.

   #. If we replace the string with a shorter one, we get an error! For
      ``word[5]`` to work, there must be a character at index 5.
   #. To prevent "index out of range" errors in this loop, we should NOT use
      a specific number inside ``range``.
   #. Replace ``range(6)`` with ``range(len(word))``. ``len(word)`` always returns
      the length of the current string, so changing that string will not break the
      loop.

Check Your Understanding
------------------------

.. admonition:: Question

   If ``phrase = 'Code for fun'``, then ``phrase[2]`` evaluates to:

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> <strong style="color:#419f6a">"o"</strong></li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, true)"> <strong style="color:#419f6a">"d"</strong></li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> <strong style="color:#419f6a">"for"</strong></li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> <strong style="color:#419f6a">"fun"</strong></li>
      </ol>
      <p id="Q1"></p>

.. Answer = b

.. admonition:: Question

   What will be printed in the THIRD iteration of the loop:

   .. sourcecode:: Python
      :linenos:

      for char in 'ABCDEFGHIJ':
         print(char)

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> <strong style="color:#419f6a">"ABC"</strong></li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> <strong style="color:#419f6a">"B"</strong></li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, true)"> <strong style="color:#419f6a">"C"</strong></li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> <strong style="color:#419f6a">"D"</strong></li>
      </ol>
      <p id="Q2"></p>

.. Answer = C

