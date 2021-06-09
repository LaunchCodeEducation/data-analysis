Can We Do Math with Boolean Values?
===================================

.. admonition:: Fun Fact

   The boolean data type is named after the British mathematician George Boole. Boole
   created `Boolean Algebra <https://en.wikipedia.org/wiki/Boolean_algebra>`__,
   which is the basis of all modern computer arithmetic.

This Fun Fact brings up the question, *Can we do math with boolean values?*

We CAN, but we probably SHOULDN'T. Boolean values are used to make decisions,
not solve calculations.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      print(True*5)
      print(False*2)
      print(True + False)
      print(True * False)

   **Console Output**

   ::

      5
      0
      1
      0

What times ``5`` gives the result ``5``? What times ``2`` gives the result
``0``?

When we use a mathematical operator (``+``, ``-``, ``*``, etc.) with boolean
values, Python automatically converts ``True`` and ``False`` to the integers
``1`` and ``0``, respectively.

Most of the time, calculations with boolean values are not very useful.
Instead, we use booleans to evaluate a *condition*.
