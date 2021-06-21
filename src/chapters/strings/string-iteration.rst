Iteration with Strings
======================

One of the most common uses of a ``for`` loop is to carry out a task on each
item in a collection. When using a loop with a collection in this way, we say
that the loop *iterates over* the collection.

Iterate by Index or Characters
------------------------------

In the Loops chapter, we learned two ways to
:ref:`iterate over a string <string-iteration>`. The following examples review
those ideas.

.. admonition:: Example

   One way to iterate over a string is to use the index values for each
   character. The following program prints each of the characters of the string
   ``'LaunchCode'`` on a separate line.
   
   Run the code to see the output, then complete the *Try It* suggestions.

   .. raw:: html

      <iframe height="450px" width="100%" src="https://repl.it/@launchcode/LCHS-String-Iteration-Example-Index?lite=true" scrolling="no" frameborder="yes" allowtransparency="true"></iframe>

   Since ``len(name)`` is 10, the loop executes once for each of the values 0 to
   9, assigning them in turn to the loop variable ``index``.

   The loop body, ``print(name[index])``, prints one of the characters from
   ``name`` (``name[0]`` through ``name[9]`` for ``'LaunchCode'``).

   **Try It!**

   #. Replace the string ``'LaunchCode'`` with your name. Note how using
      ``len(name)`` as the argument inside ``range`` makes the loop run the
      proper number of times, regardless of the string.
   #. Use ``range(start, stop, step)`` to print every third character from
      ``name``.
   #. Loop through the string using *negative* index values. Run the program
      with ``range(-1, -len(range), -1)``. How does the output change?
   #. ``range(-1, -len(range), -1)`` does not quite get all of the letters from
      ``name``. Modify the ``start, stop, step`` values as needed to print all
      of the characters.

Since a string is simply a sequence of characters, Python gives us a way to
automatically iterate over those characters.

.. admonition:: Example
   
   Run the following code to see the output, then complete the *Try It*
   suggestions.

   .. raw:: html

      <iframe height="450px" width="100%" src="https://repl.it/@launchcode/LCHS-String-Iteration-Example-chars?lite=true" scrolling="no" frameborder="yes" allowtransparency="true"></iframe>

   The loop variable ``char`` is automatically reassigned each character in the
   string stored by ``fruit``. This approach is called *iteration by item*.

   We also see an example of the accumulator pattern. The program reassigns a
   new, longer string to ``fruit_copy`` each iteration.
   
   Note that *iteration by item* moves through a collection from left to right.
   If we want to move from right to left, we must use the index values.

   **Try It!**

   #. Replace ``fruit_copy += char`` with
      ``fruit_copy = char.upper() + fruit_copy``. What happens to the output?
   #. Replace ``print(char, fruit_copy)`` with
      ``print(char, fruit.count(char))``. Run the program to see the output.
   #. Use a template literal and ``format()`` to print a more readable message
      each iteration. Something like, ``'Bananas' contains 3 'a' character(s).``
      The output should change each time the loop repeats.

Check Your Understanding
------------------------

.. admonition:: Question

   Given the following code, which character is printed during the *fifth*
   iteration?

   .. sourcecode:: Python
      :linenos:

      text = 'Hello, World!'

      for index in range(len(text)):
         print(text[index])
      
   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">'l'</span></li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, true)"> <span style="color:#419f6a; font-weight: bold">'o'</span></li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">','</span></li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">' '</span></li>
      </ol>
      <p id="Q1"></p>

.. Answer = b

.. admonition:: Question

   Given the following code, which character is printed during the *fifth*
   iteration?

   .. sourcecode:: Python
      :linenos:

      text = 'Hello, World!'

      for char in text:
         print(char)
      
   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">'l'</span></li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, true)"> <span style="color:#419f6a; font-weight: bold">'o'</span></li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">','</span></li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">' '</span></li>
      </ol>
      <p id="Q2"></p>

.. Answer = b

.. admonition:: Question

   Given the string ``my_dream_car = 'Tesla'``, which of the following will
   loop backwards through all of the characters in the string? Select ALL
   options that work.

   .. raw:: html
      
      <ol type="a">
         <li><span id = "a" onclick="highlight('a', false)">for index in range(len(my_dream_car)):</span></li>
         <li><span id = "b" onclick="highlight('b', false)">for index in range(-1, -len(my_dream_car), -1):</span></li>
         <li><span id = "c" onclick="highlight('c', true)">for index in range(len(my_dream_car)-1, -1, -1):</span></li>
         <li><span id = "d" onclick="highlight('d', true)">for index in range(-1, -len(my_dream_car)-1, -1):</span></li>
         <li><span id = "e" onclick="highlight('e', false)">for char in my_dream_car:</span></li>
         <li><span id = "f" onclick="highlight('f', false)">for char in -my_dream_car:</span></li>
      </ol>

.. Answers = c & d

