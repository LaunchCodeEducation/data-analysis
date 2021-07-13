String Immutability
===================

.. index:: ! immutable

If an object cannot be changed, we say that it is **immutable**. Strings are
immutable, which means we cannot change the individual characters within a
string. While we can access individual characters using bracket notation,
trying to change individual characters simply does not work.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      title = 'The princess Bride'

      title[4] = 'P'

   **Console Output**

   ::

      Traceback (most recent call last):
      line 3
      title[4] = 'P'
      TypeError: 'str' object does not support item assignment

On line 3, we tried to change the character at index 4 from ``'p'`` to
``'P'`` by using an assignment statement along with bracket notation. However,
the attempt caused an error and crashed the program.

Reassign Variables
------------------

It is important to notice that immutability applies to string *values* and not
string *variables*.

.. admonition:: Example

   We can assign a different value to a variable containing a string.

   .. sourcecode:: python
      :linenos:

      title = 'The princess Bride'

      title = 'The Princess Bride'

      print(title)

   **Console Output**

   ::

      The Princess Bride

In this example, the change made on line 3 works. The difference between this
example and the first is that here we assign a new value to the variable. We
are not trying to change the original string itself. If we picture a variable
as a label that *points to* a value, the second example has the following
effect:

.. figure:: ./figures/string-var-reassignment.png
   :alt: A variable, ``title``, pointing at "The Princess Bride" with an uppercase P.
   :scale: 80%

   When the value of a variable storing a string is changed, the variable then
   points to a new value, with the old value remaining unchanged.

.. admonition:: Note

   Reassigning the value of a variable might look like we are changing the
   string, but we are not. Instead, we just replace the old, unchanged string
   with a different one.

   .. sourcecode:: python
      :linenos:

      pet = 'dog'
      print(pet + 's')  # Create and print a new string.
      print(pet)        # The original string remains unchanged.

      pet = 'cat'       # Assign a new, different string to the variable pet.
      print(pet)        # Print the new value. 'dog' was replaced, NOT changed.

      pet += 's'        # This LOOKS like we are adding 's' to 'cat', but instead
      print(pet)        # we are replacing 'cat' with the new string 'cats'.
   
   **Console Output**

   ::

      dogs
      dog
      cat
      cats

Check Your Understanding
------------------------

.. admonition:: Question

   Given ``pet = 'cat'``, why do the statements ``print(pet + 's')`` and
   ``pet += 's'`` NOT violate the immutability of strings?
