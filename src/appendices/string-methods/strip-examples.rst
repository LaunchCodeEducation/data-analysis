.. _string-strip-examples:

.. index::
   single: string; strip

``strip`` Examples
==================

The general syntax for this method is:

.. sourcecode:: python

   string_name.strip()

.. index:: ! whitespace

This method returns a copy of the string with any leading or trailing spaces
removed. **Whitespace** characters are those that do not display anything on
the screen, such as spaces, tabs, and new lines.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      print("  Saint Louis      " + '.')
      print("Saint Louis\n")              # \n adds a newline to the string.
      print("\tSaint Louis")              # \t adds a tab to the string.

      print('----')

      print("  Saint Louis      ".strip() + '.')
      print("Saint Louis\n".strip())
      print("\tSaint Louis".strip())

   **Console Output**

   .. sourcecode:: bash

        Saint Louis      .
      Saint Louis

          Saint Louis
      ----
      Saint Louis.
      Saint Louis
      Saint Louis

Note that the ``strip`` method does NOT remove any whitespace from the middle
of a string.

.. admonition:: Example

   When typing an email address into a web site, a user might accidentally add
   a space before and/or after the address. We can clean up the input with the
   ``strip`` method.

   .. sourcecode:: python
      :linenos:

      user_input = " fake.email@launchcode.org "
      email = user_input.strip()
      print(email)

   **Console Output**

   ::

      fake.email@launchcode.org

More Than Spaces
----------------

By default, the ``strip`` method removes any leading or trailing whitespace from
a string. However, we can also remove ANY characters of our choice from the
start and end of a string.

The syntax for this is:

.. sourcecode:: python

   string_name.strip('characters')

``characters`` is a string containing all the characters we want to remove.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      text = "   ... @ Rutabagas in the spring!!!!*!*!*!*!"

      print(text.strip())        # Removes leading whitespace before '...'.
      print(text.strip('!'))     # Removes the single trailing '!' character.
      print(text.strip('. !'))   # Removes leading and trailing '.', space, and '!'.
      print(text.strip('. !*@')) # Removes leading and trailing '.', space, '!', '*', and '@'.
   
   **Console Output**

   ::

      ... @ Rutabagas in the spring!!!!*!*!*!*!
         ... @ Rutabagas in the spring!!!!*!*!*!*
      @ Rutabagas in the spring!!!!*!*!*!*
      Rutabagas in the spring
