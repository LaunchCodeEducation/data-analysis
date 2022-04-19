.. index::
   single: list; join

.. _list-join-examples:

``join`` Examples
=================

The general syntax for this method is:

.. sourcecode:: python

   'connecter'.join(list_name)

``join`` combines all of the elements in ``list_name`` into a single string.
Note that each element in ``list_name`` MUST be a string data type.

The ``'connector'`` determines the string that "glues" the list elements
together. ``'connector'`` may be the empty string (``''``), any single
character, multiple characters, or special characters (like ``'\t'`` or
``'\n'``).

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      digit_strings = ['1', '2', '3', '4']
      words = ['Hello', 'World', '!']
      new_string = ''

      new_string = '+'.join(digit_strings)
      print(new_string)

      new_string = ''.join(words)
      print(new_string)

      new_string = '\n'.join(words)
      print(new_string)

   **Output**

   ::

      1+2+3+4
      HelloWorld!
      Hello
      World
      !
