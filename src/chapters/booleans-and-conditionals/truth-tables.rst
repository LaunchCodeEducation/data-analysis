Truth Tables
============

.. index:: ! truth table

**Truth tables** help us understand how logical operators work by showing all
of the possible return values. Let's look at the truth table for ``and``, which
assumes we have two boolean expressions, ``A`` and ``B``.

.. admonition:: Example

   .. list-table:: Truth Table for ``and``
      :widths: auto
      :header-rows: 1

      * - A
        - B
        - A ``and`` B
      * - ``True``
        - ``True``
        - ``True``
      * - ``True``
        - ``False``
        - ``False``
      * - ``False``
        - ``True``
        - ``False``
      * - ``False``
        - ``False``
        - ``False``

Consider the first row of the table. This row states that if A is true
and B is true, then ``A and B`` is true. The two middle rows show that if
either A or B is false, then ``A and B`` is false. Finally, if both A and B are
false, then ``A and B`` is false.

.. admonition:: Try It!

   Now take a look at the truth table for ``or``.

   #. PREDICT whether ``A or B`` should be ``True`` or ``False`` for each row.
   #. Click in the empty spaces to check your answers.

   .. list-table:: Truth Table for ``or``
      :widths: auto
      :header-rows: 1

      * - A
        - B
        - A ``or`` B
      * - ``True``
        - ``True``
        - .. raw:: html

             <b id = "optionA" onclick="reveal('optionA')" style="opacity:0">True</b>

      * - ``True``
        - ``False``
        - .. raw:: html

             <b id = "optionB" onclick="reveal('optionB')" style="opacity:0">True</b>

      * - ``False``
        - ``True``
        - .. raw:: html

             <b id = "optionC" onclick="reveal('optionC')" style="opacity:0">True</b>

      * - ``False``
        - ``False``
        - .. raw:: html

             <b id = "optionD" onclick="reveal('optionD')" style="opacity:0">False</b>

Order of Operations
-------------------

.. index:: order of operations

We now have a lot of operators in our toolkit, so it is important to understand
how they relate to each other. Which operators get done first?

Python always performs operations in a specific order:

#. It does all math calculations first.
#. Next, it evaluates all comparisons as ``True`` or ``False``.
#. Next, it applies all ``not`` operators.
#. Finally, it evaluates ``and`` and ``or`` operations.

.. admonition:: Example

   The expression ``x * 5 >= 10 and y - 6 <= 20`` will be completed in this order:

   #. ``x * 5`` is calculated, then ``y - 6``.
   #. The ``>=`` comparison is evaluated as ``True`` or ``False``.
   #. The ``<=`` comparison is evaluated as ``True`` or ``False``.
   #. The ``and`` operator is evaluated last.

   Let's say ``x = 2`` and ``y = 46``. Here we step through each stage of the evaluation:
     
   .. list-table:: Operator Order on: ``x * 5 >= 10 and y - 6 <= 20``
      :widths: auto
      :header-rows: 1

      * - Action
        - Result
      * - Plug in the values into the expression
        - ``2 * 5 >= 10 and 46 - 6 <= 20``
      * - ``x * 5`` is calculated, then ``y - 6``
        - ``10 >= 10 and 40 <= 20``
      * - The ``>=`` comparison is evaluated as ``True`` or ``False``
        - ``True and 40 <= 20``
      * - The ``<=`` comparison is evaluated as ``True`` or ``False``
        - ``True and False``
      * - The ``and`` operator is evaluated last
        - ``False``


Table of Operator Order
^^^^^^^^^^^^^^^^^^^^^^^

The following table lists operators in order of importance, from highest
(applied first) to lowest (applied last).

.. list-table:: Operator Order
   :widths: auto
   :header-rows: 1

   * - Level
     - Category
     - Operators
   * - (Highest)
     - Parentheses
     - ``()``
   * -
     - Exponent
     - ``**`` (For example: ``2**3``)
   * -
     - Multiplication and Division
     - ``*  /  //  %``
   * -
     - Addition and subtraction
     - ``+  -``
   * -
     - Comparison
     - ``==  !=  <=  >=  >  <``
   * -
     - Logical
     - ``not``
   * -
     - Logical
     - ``and``
   * - (Lowest)
     - Logical
     - ``or``

.. admonition:: Tip

   Using parentheses is not always necessary, but they make a BIG difference when
   someone else reads your code. As a best practice, use parentheses to make your 
   code easier to read:

   ``x * 5 >= 10 and y - 6 <= 20``

   vs.

   ``(x * 5 >= 10) and (y - 6 <= 20)``

Check Your Understanding
------------------------

.. admonition:: Question

   Assume we have 3 boolean expressions (A, B, and C). Which combinations of
   values (A/B/C) will make the expression ``A or B and C`` evaluate to
   ``True``? Click ALL that apply.

   .. raw:: html

      <ol type="a">
         <li><span id = "a" onclick="highlight('a', true)">True / True / True</span></li>
         <li><span id = "b" onclick="highlight('b', true)">False / True / True</span></li>
         <li><span id = "c" onclick="highlight('c', true)">True / False / True</span></li>
         <li><span id = "d" onclick="highlight('d', true)">True / True / False</span></li>
         <li><span id = "e" onclick="highlight('e', false)">False / False / True</span></li>
         <li><span id = "f" onclick="highlight('f', false)">False / True / False</span></li>
         <li><span id = "g" onclick="highlight('g', true)">True / False / False</span></li>
         <li><span id = "h" onclick="highlight('h', false)">False / False / False</span></li>
      </ol>

.. Answers = a, b, c, d, g
