Logical Operators
=================

.. index:: operator

.. index::
   single: operator; comparison
   single: operator; boolean
   single: operator; logical

Recall that an *operator* carries out an action on one or more operands
(values). Math operators (``+``, ``-``, ``*``, ``/``, ``//``, ``**``, ``%``)
perform calculations. **Boolean operators** (like the comparisons ``==`` and
``<``) return a value of either ``True`` or ``False``.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      name = input('Please enter a username: ')

      if len(name) > 5:
         print("Welcome, " + name + "!")
      else:
         print("Invalid username.")

   The expression ``len(name) > 5`` compares the length of the string stored
   in ``name`` to the value ``5``.

   If ``False``, the program prints ``Invalid username.`` If ``True``, the
   program prints the welcome message.

What if we wanted to set another limit to the length of ``name``? We could
replace line 3 with ``if len(name) < 10``, but then we would lose the first
comparison. Fortunately, we can perform both checks at the same time.

Three boolean operators allow us to make more complicated comparisons in a
single ``if`` statement. These are called **logical operators**, and there
are only three---``and``, ``or``, and ``not``.

Logical ``and``
---------------

.. index:: ! and

.. index::
   single: boolean; expression, compound

Let's take the two boolean expressions from above:

#. ``len(name) > 5`` returns ``True`` when ``name`` contains more than 5
   characters.
#. ``len(name) < 10`` returns ``True`` when ``name`` contains less than 10
   characters.

A **compound boolean expression** is a boolean expression built out of smaller
ones. Python allows us to combine expressions by using the ``and`` operator.

.. sourcecode:: Python

   len(name) > 5 and len(name) < 10

Run the following code and examine the output. Try each of the ``name``
suggestions to see how they change the output.

.. raw:: html

   <iframe height="400px" width="100%" src="https://repl.it/@launchcode/Explore-logical-and?lite=true" scrolling="no" frameborder="no" allowtransparency="true"></iframe>

A compound expression returns only ONE boolean value, which depends on the
results from BOTH of the smaller comparisons.
``len(name) > 5 and len(name) < 10`` is true only if ``len(name)`` is
greater than ``5`` AND, at the same time, ``len(name)`` is less than ``10``.

.. admonition:: Take-Home Idea

   #. Logical ``and`` combines two conditions.
   #. The combined expression is ``True`` only if *both* conditions return
      ``True``.
   #. If either condition is ``False``, the overall expression is ``False``.

.. admonition:: Tip

   The meaning of ``and`` resembles its use in English. The sentence "Roses
   are red and violets are blue," is true as a whole because roses are
   actually red, and violets are blue.

   On the other hand, the sentence "Roses are red and violets are green," is
   false as a whole. While roses are indeed red, violets are NOT green.

Let's look at another example.

.. admonition:: Example

   .. sourcecode:: Python
      :linenos:

      num = 5
      print(num > 0 and num < 10)

      print(7 > num and num == 3)

      print(num*5 > 100 and 'dog' == 'cat')

   **Console Output**

   ::

      True
      False
      False

In line 2, ``num > 0 and num < 10`` evaluates to ``True`` because both
``num > 0`` and ``num < 10`` are each ``True``.

In line 4, the expression ``7 > num and num == 3`` evaluates to ``False``
because one of the two comparisons, ``num == 3``, is ``False``.

Line 6 evaluates to ``False`` because both comparisons return ``False``.
Notice that we can mix and match data types however we like, as long as both
sides of the ``and`` expression are themselves boolean expressions.

Logical ``or``
--------------

.. index:: ! or

Python's logical ``or`` also combines two boolean expressions. In this case,
however, the resulting expression is ``True`` if *either* of the conditions are
``True``. If both conditions are ``False``, the overall expression is
``False``.

For the compound expression ``num - 2 == 0 or num - 3 == 0``, only one part has
to be true for the overall result to be ``True``.

Let's look at another code example. Change the value of ``num`` to see when
each combined expression returns ``True``.

.. raw:: html

   <iframe height="350px" width="100%" src="https://repl.it/@launchcode/Explore-logical-or?lite=true" scrolling="no" frameborder="no" allowtransparency="true"></iframe>

Using ``num = 5``, lines 2 and 4 both return ``True`` because at least one of
the two comparisons is ``True``. Line 6 returns ``False`` because both of the
comparisons are ``False``.

.. admonition:: Tip

   Logical ``or`` also resembles its English use. The sentence "Pigs can
   fly, or dogs can run," is true as a whole. Even though pigs cannot fly, dogs
   CAN run. Only one of the two statements has to be true in order for the whole
   sentence to be true.

   When both of the statements joined by ``or`` are false, the statement as a
   whole is false. "Pigs can fly or the Earth is flat," is a false statement.

Logical ``not``
---------------

.. index:: ! not

The logical ``not`` operator takes a single operand and flips its boolean
value. If a comparison returns ``False``, then applying ``not`` changes the
result to ``True`` (and vice versa).

.. admonition:: Examples

   .. sourcecode:: python
      :linenos:

      print(not True)
      print(not False)

      num = 5

      print( not(num < 7) )
      print( not('dog' == 'cat') )
      print( not(num*5 > 100 or 'dog' == 'cat') )

   **Console Output**

   ::

      False
      True
      False
      True
      True

Longer Combinations
-------------------

In the examples above, we used the ``and`` and ``or`` operators to combine two
smaller boolean expressions. However, we can use the operators to combine as
many expressions as we want!

.. sourcecode:: Python
   :linenos:

   num = 5
   python = 'Awesome!'

   print(num > 0 and num < 10 and 'dog' == 'cat')
   print(num > 7 or num == 3 or 'dog' == 'cat' or python == 'Awesome!')

**Console Output**

::

   False
   True

.. admonition:: Warning

   Here is a VERY common mistake programmers make when they try to combine
   boolean expressions.

   What if we have a variable ``num`` and we want to check if its value is 5, 6,
   or 7?

   #. If we try to describe this out loud, we might say, “``num`` is equal to 5 or 6
      or 7”.
   #. If we translate this into Python as ``num == 5 or 6 or 7``, we get an
      error when we run the code.

   To prevent this error, we must combine three separate equality comparisons,
   ``num == 5 or num == 6 or num == 7``. This may seem like a lot of extra
   typing, but it is necessary.

Check Your Understanding
------------------------

.. admonition:: Question

   What is returned by the following boolean expression?

   .. sourcecode:: python

      4 < 3 or 2 < 3

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, true)"> <code class="pre">True</code></li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> <code class="pre">False</code></li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> <code class="pre">"True"</code></li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> <code class="pre">"False"</code></li>
      </ol>
      <p id="Q1"></p>

.. Answer = a

.. admonition:: Question

   What is the correct Python expression for checking to see if a number
   stored in the variable ``num`` is between 0 and 5.

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> <code class="pre">num > 0 and < 5</code></li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> <code class="pre">num > 0 or < 5</code></li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, true)"> <code class="pre">num > 0 and num < 5</code></li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> <code class="pre">num > 0 or num < 5</code></li>
      </ol>
      <p id="Q2"></p>

.. Answer = c

.. admonition:: Question

   Predict if each of the following expressions evaluates to ``True`` or
   ``False``. Click on each one to check your answers.

   .. raw:: html

      <ol type="a">
         <li onclick="revealTrueFalse('resultA', true)"><code class="pre">12 * 2 == 24</code> <span id="resultA"></span></li>
         <li onclick="revealTrueFalse('resultB', false)"><code class="pre">'dog' == 'cat or 'dog' == 'Dog'</code> <span id="resultB"></span></li>
         <li onclick="revealTrueFalse('resultC', false)"><code class="pre">12%2 == 0 and len('flower') < 6</code> <span id="resultC"></span></li>
         <li onclick="revealTrueFalse('resultD', true)"><code class="pre">'a' in 'xyz' and len('flower') >= 6 or 5 + 5 == 10</code> <span id="resultD"></span></li>
      </ol>

.. Answer = True, False, False, True
