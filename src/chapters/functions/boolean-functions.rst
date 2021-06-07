Boolean Functions
=================

.. _boolean-function:

.. index::
   pair: function; boolean

A function that returns a boolean value (``True`` or ``False``) is known as a
**boolean function**. One simple example tests if an integer is even or odd.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      def is_int_even(integer):
         if integer % 2 == 0:
            return True
         else:
            return False

      print(is_int_even(4))
      print(is_int_even(7))

   **Console Output**

   ::

      True
      False

.. admonition:: Tip

   Start the names of boolean functions with either ``is`` or ``has``, which
   helps make their purpose more clear. For example, reading ``is_int_even(4)``
   tells us that the function should answer the question: "Is the integer 4
   even?"
   
   This convention is so widely used by programmers that it extends to nearly
   every language.

Let's look at ``is_int_even`` again to see how we can use the power of
``return`` statements to make it even stronger.

Since ``return`` ends the function, we can leave out the ``else`` clause and
have the same effect. If ``integer`` is even, the return statement in line 3
runs, and the function ends. If ``integer`` is odd, the ``if`` block gets
skipped and the second return statement executes.

.. sourcecode:: python
   :linenos:

   def is_int_even(integer):
      if integer % 2 == 0:
         return True

      return False

   print(is_int_even(4))
   print(is_int_even(7))

The updated version returns the same results as the original and contains less code. 

The function returns ``True`` when the expression
``integer % 2 == 0`` is ``True``, and the function returns ``False`` when
``integer % 2 == 0`` is ``False``. In this case, the return value is *exactly
the same* as the value of ``integer % 2 == 0``. This means that we can
simplify the function even more by returning the result of the expression!

.. sourcecode:: python
   :linenos:

   def is_int_even(integer):
      return integer % 2 == 0

   print(is_int_even(4))
   print(is_int_even(7))

This version of ``is_int_even`` is better than the first two, not because it is
shorter (shorter isn't always better), but because it is simpler to read. We
don't have to break down the conditional logic to see what is being returned.

Most boolean functions can be written so that they return the result of a
boolean expression, rather than directly returning ``True`` or ``False``.

Try It!
-------

.. admonition:: Example

   Complete the ``is_capitalized`` function to return ``True`` if a string
   begins with a capital letter and ``False`` otherwise.

   .. raw:: html

      <iframe src="https://trinket.io/embed/python3/92ac6b2101?runOption=run" width="100%" height="350" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

   *Hints*:

   #. How do you access the *first* character in a string?
   #. The ``in`` operator will be useful, or you can try the ``.isupper()``
      method.

.. admonition:: Example

   Complete the ``is_answer_correct`` function to return ``True`` if a user's
   answer matches the correct response. The check should be *case-insensitive*.

   .. raw:: html

      <iframe src="https://trinket.io/embed/python3/e826e9a6f6?runOption=run" width="100%" height="500" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

   With the given answer pairs, the program should count 2 correct responses.
