Checking Strings
================

It is often helpful to examine a character and test whether it is uppercase,
lowercase, or whether it is a character or a digit.

We can use bracket notation and string methods inside a
:ref:`boolean expression <boolean-expression>` to check if a string meets a
certain condition.

Checking Type
-------------

The string methods only work on string objects. Let's say ``my_var = 'Python'``.

``my_var.upper()`` works just fine. However, if we were to reassign a number
to the variable, like ``my_var = 3.14159``, then ``my_var.upper()`` throws an
error.

Let's see how we can use the ``type()`` function to check for a string.

.. admonition:: Example

   .. raw:: html

      <iframe height="500px" width="100%" src="https://repl.it/@launchcode/LCHS-String-Conditionals-Practice?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true"></iframe>

   Run the program with each of the following values for ``my_var``:

   #. ``'1234'`` vs. ``1234``
   #. ``True`` or ``False`` vs. ``"True"`` or ``"False"``
   #. ``0.333`` vs. ``'0.333'``

   **Follow Up**:

   #. Add an ``elif`` statement and code block to check for the ``int`` data
      type.
   #. Repeat this process for the ``float`` and ``bool`` data types.
   #. Rerun the program with the different ``my_var`` values.
      
We can easily modify line 3 to check if ``my_var`` is an ``int``, ``float``,
or ``bool`` data type. We could also use an ``if/elif/else`` block to check for
the different data types.  (*TRY IT*!)

.. admonition:: Note

   Of course, we could avoid the conditional block completely with:

   .. sourcecode:: Python

      print("The value {0} is a {1} data type.".format(my_var, type(my_var))

Comparing Strings
-----------------

We can use the comparison operators ``==, !=, <, >, <=, >=`` on strings.

.. admonition:: Example

   .. sourcecode:: Python
      :linenos:

      my_pet = 'dog'
      your_pet = 'cat'
      other_pet = 'crow'

      print(my_pet == your_pet)
      print(your_pet[0] == other_pet[0])
      print(my_pet < your_pet)
   
   **Console Output**

   ::

      False
      True
      False

#. Line 5 evaluates if the strings ``'dog'`` and ``'cat'`` are identical and
   then prints the boolean result (``False``).
#. Line 6 evaluates if the first character in ``'cat'`` and ``'crow'`` are the
   same (``True``).

   - Note that the first character comparison for ``'cat'`` and ``'Crow'``
     would return ``False`` due to the different cases.
   - To make the expression *case-insensitive*, we need to convert each
     character to the same case (e.g.
     ``your_pet[0].lower() == other_pet[0].lower()``).

#. Line 7 evaluates if ``'dog'`` is less than ``'cat'``. This comparison is a bit more complicated.
   What is really being compared is each character's Unicode value. All characters, even letters,
   have `Unicode numbers <https://unicode-table.com/en/>`__. The Unicode value of a letter corresponds with its alphabetical order. 
   So a string that comes earlier in the alphabet is considered *less than* a string that comes
   later. Since ``'dog'`` follows ``'cat'`` alphabetically, the expression
   ``'dog' < 'cat'`` evaluates to ``False``.
   
.. admonition:: Note

   Case matters when comparing characters! CAPITAL letters have smaller Unicode values
   than lowercase letters.

   ``'Zebra' < 'zebra'`` is ``True``,

   ``'Zebra' < 'apple'`` is ``True``,  and 

   ``'zebra' < 'apple'`` is ``False``.

Checking with ``in`` and ``not in``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If we want to find out if a certain character is in a string, we could iterate
through the string and compare each character to the one we want.

.. sourcecode:: Python
   :linenos:

   title = 'The Hunger Games'
   search_character = 'e'

   for char in title:
      if char == search_character:
         print("'{0}' is in '{1}'.".format(search_character, title))

However, this is inefficient, since the loop continues even after we find
``search_character``. As coded, the program prints the output once each time
``search_character`` is found.

A better approach is to use the ``in`` operator (or its opposite, ``not in``)
to return the same information. The ``in`` operator tests if one string is a
substring of another.

.. sourcecode:: Python
   :linenos:

   title = 'The Hunger Games'
   search_character = 'e'

   if search_character in title:
      print("'{0}' is in '{1}'.".format(search_character, title))

.. admonition:: Try It!

   This example uses the ``in`` operator to decide when to increase the value
   of ``vowel_count``.

   .. raw:: html

      <iframe height="600px" width="100%" src="https://repl.it/@launchcode/LCHS-Conting-Vowels-Example?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true"></iframe>

   #. The program does not quite work yet. There are 9 vowels in
      ``'Armadillos or anteaters'``, but the code does not count the capital
      ``A``.
   #. Fix the code to be *case-insensitive*. Both capital and lowercase vowels
      should increase ``vowel_count``.
   #. Refactor the code to report the number of consonants (non-vowels) in the
      string. (*Hint*: Use the ``not in`` operator).

Checking Case
-------------

Let's explore how we can check the case for a character, slice, or an entire
string. Fortunately, Python provides methods that check the case of a string, and they
deal with non-letter characters properly.

.. admonition:: Example

   .. sourcecode:: Python
      :linenos:

      character = 'a'
      word = "yep!"
      non_letters = '$10.75'

      print(character.isupper())
      print(word.islower())
      print(non_letters.isupper())
   
   **Console Output**

   ::

      False
      True
      False

The ``isupper()`` method returns ``True`` if all the letters in a string are
uppercase. If the string contains a single lowercase letter, or no letters at
all, the method returns ``False``. The ``islower()`` method behaves in a
similar way, but it checks for lowercase letters.

Check Your Understanding
------------------------

Evaluate whether the following expressions are ``True`` or ``False``:

.. admonition:: Question

   .. sourcecode:: Python

      "dog" < "doghouse"

   .. raw:: html
   
      <ol type="a">
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, true)"> <span style="color:#419f6a; font-weight: bold">True</span></li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">False</span></li>
      </ol>
      <p id="Q1"></p>

.. Answer = True

.. admonition:: Question

   .. sourcecode:: Python

      "dog" < "Dog"

   .. raw:: html
   
      <ol type="a">
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">True</span></li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, true)"> <span style="color:#419f6a; font-weight: bold">False</span></li>
      </ol>
      <p id="Q2"></p>

.. Answer = False

.. admonition:: Question

   .. sourcecode:: Python

      "dog" < "Doghouse"
   
   .. raw:: html
   
      <ol type="a">
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">True</span></li>
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, true)"> <span style="color:#419f6a; font-weight: bold">False</span></li>
      </ol>
      <p id="Q3"></p>

.. Answer = False

.. admonition:: Question

   .. sourcecode:: Python

      "app" in "Happy"

   .. raw:: html
   
      <ol type="a">
         <li><input type="radio" name="Q4" autocomplete="off" onclick="evaluateMC(name, true)"> <span style="color:#419f6a; font-weight: bold">True</span></li>
         <li><input type="radio" name="Q4" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">False</span></li>
      </ol>
      <p id="Q4"></p>

.. Answer = True 

.. admonition:: Question

   For which of the following would ``text.upper() == text`` return
   ``True``?

   .. raw:: html
   
      <ol type="a">
         <li><input type="radio" name="Q5" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">text = 'Stop Yelling!'</span></li>
         <li><input type="radio" name="Q5" autocomplete="off" onclick="evaluateMC(name, true)"> <span style="color:#419f6a; font-weight: bold">text = 'STOP YELLING!'</span></li>
         <li><input type="radio" name="Q5" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">text = 'stop yelling!'</span></li>
         <li><input type="radio" name="Q5" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">text = 'STOP YELLINg!'</span></li>
         <li><input type="radio" name="Q5" autocomplete="off" onclick="evaluateMC(name, false)"> All return <span style="color:#419f6a; font-weight: bold">True</span></li>
         <li><input type="radio" name="Q5" autocomplete="off" onclick="evaluateMC(name, false)"> None return <span style="color:#419f6a; font-weight: bold">True</span></li>
      </ol>
      <p id="Q5"></p>

.. Answer = b

