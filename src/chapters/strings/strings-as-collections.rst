Strings as Collections
======================

Throughout the first chapters of this book, we use strings to represent words,
phrases, or characters we want to print. Our first definition of a string is
simple: *a string is a sequence of characters inside quotes*.

In this chapter we explore strings in much more detail.

Collection Data Types
---------------------

.. index:: ! collection

.. index::
   single: data type; collection

Strings are an example of a **collection data type**. *Collections* are built
from smaller, individual pieces. Other data types like ``int``, ``float``, and
``bool`` do NOT contain any smaller parts.

Depending on what we are doing, we can treat a collection data type as a single
object, like a cardboard box, or we can dig into the collection and access its
smaller parts (searching through the box).

.. index:: ! character

A **character** is a string that contains exactly one element, such as ``'a'``,
``"?"``, or even ``" "`` (a single space character).

Strings are built out of these single characters. In this way, strings can be
broken down into smaller pieces.

.. figure:: ./figures/python-string.png
   :alt: The string "Python" broken down into individual letters.

   The string "Python" is made up of 6 characters, each of which is a string of
   length 1.

Ordered Collections
-------------------

.. index::
   single: collection; ordered

We also call strings **ordered collections** of characters. This means that the
individual characters in the string follow a particular order from left to
right. The string ``"LaunchCode"`` is different from the string
``"CodeLaunch"``, even though they contain the exact same characters.

Collection Length
-----------------

.. index:: ! len

Strings can contain any number of characters, and we often need to determine
how many are in the collection. Fortunately, Python gives us a convenient
function to return this value.

The **length function**, ``len()``, returns the number of elements inside of a
collection. We can put the collection itself inside the parentheses, like
``len('hello')``, or we can use a variable.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      text = "Don't count the number of characters yourself. Python will do it for you!"

      length_of_text = len(text)
      print(length_of_text)

   **Console Output**

   ::

      73

   Note that any spaces in a string also count as characters.

The Empty String
^^^^^^^^^^^^^^^^

.. index:: ! empty string

A string that contains no characters, called the **empty string**, is still
considered a string. It simply contains zero characters and is represented by
``''`` or ``""`` (two single or two double quotes with nothing in between).

We used an empty string before, when we practiced the
:ref:`accumulator pattern <accumulator-pattern>`.

Quote Reminder
--------------

Recall from the :ref:`Data and Variables <quote-reminder>` chapter that we can
use single quotes around a string (``'hello'``), double quotes (``"hello"``),
or triple quotes (``'''hello'''`` and ``"""hello"""``), as long as we start and
end with the same type.

Why have three options?

#. We can include quote characters inside a string, as long as we use a
   different type around the entire collection. For example, ``"The teacher's
   classroom."`` or ``'''"Quote from a book, with the author's name."'''``).
#. Triple quotes allow us to create strings that cover multiple lines.

   .. sourcecode:: Python
      :linenos:

      sentence = '''This string covers
      multiple lines.
      Cool!'''

      print(sentence)

   **Console Output**

   ::

      This string covers
      multiple lines.
      Cool!
