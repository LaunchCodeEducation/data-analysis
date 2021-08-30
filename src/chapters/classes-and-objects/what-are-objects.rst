What are Objects
================

A quick search of the web returns this fact:

   Python is an Object-Oriented Programming language.

Object-oriented programming (OOP) is a software design model that focuses on
the capabilities of *object types* instead of on things like individual
functions, loops, logic, etc. In this book, we won't get into the principles
behind OOP. However, we do need to take a closer look at the concept of
*objects*.

We have worked with objects many times already: string objects,
list objects, etc. However, we never explained what objects represent in
Python.

As a first step, let's review some vocabulary:

#. A *value* is a specific piece of data, like the integer ``3``, the string
   ``'hello'``, or the list ``[33, 45.2, 8]``.
#. A *function* is a defined, reusable block of code that performs a single,
   small task.

We assign values to variables so we can use the data later in our program. We
define and call functions to do something with data or perform actions on it.
When we set up our programs this way, data storage and data manipulation get
carried out separately.

.. index:: ! object

**Objects** do both. They store data *and* perform actions on that data.
Objects give us a way to bring together all the parts of our code that relate
to each other.

.. index:: ! method, ! property

The data assigned to an object is called its **properties**. The actions an
object can perform are called its **methods**.

.. admonition:: Tip

   Think of an object like a smart phone.

   The *properties* of an object give us information about it. For a phone,
   this data includes things like brand, size, mass, color, amount of memory,
   etc.

   The *methods* of an object determine what it can *do*. For a phone, this
   would be the apps it contains. These allow the object to do things like take
   photos, send text messages, pay a bill, or even make a voice call.

Examples of Objects
-------------------

Let's begin with a familiar example: strings.

.. sourcecode:: Python

   text = "I am an object."

All strings have a length property. This tells us the number of characters
between the quote marks. Each individual character can be classified as a
letter, digit, punctuation, etc. Strings also include a property that describes
their case (upper or lower).

In addition to these properties, we can perform a defined set of actions on ANY
string value. :ref:`These methods <string-methods-appendix>` take the original
string as data and return a new string. Examples include ``.upper()`` and
``.split()``.

Since strings contain both properties and methods (data and behaviors), they
are objects.

Objects Organize Related Code
-----------------------------

All strings can use the same set of methods. However, if we try to use
``.upper()`` on an integer, list, or anything other than a string, Python
throws an error message. Similarly, the ``.pop()`` method only works with
list or dictionary objects.

.. admonition:: Example

   .. sourcecode:: Python
      :linenos:

      words = ['a', 'an', 'the']

      print(words.upper())

   **Console Output**

   ::

      Line 3,
         print(words.upper())
      AttributeError: 'list' object has no attribute 'upper'

   Even though each element in ``words`` is a string, the list itself is NOT a
   string object.

Objects help us by keeping related code in one place. For example, the method
``.sort()`` makes sense for a list, but may not make sense for other objects. Thus, every ``list``
object contains the code to rearrange the elements, but other objects do not.

If we define a new ``elephant`` type of object, then that kind of object only
contains code to deal with elephant data and elephant behaviors. Any code not
related to elephants belongs somewhere else in our program.

Check Your Understanding
------------------------

.. admonition:: Question

   Assume we create an object of type ``rabbit`` in our code. Which of the
   following are *methods* for this kind of object?

   a. size
   b. chew_flowers
   c. invade_garden
   d. age
   e. run
   f. color

.. Methods = b, c, e.


.. admonition:: Question

   In our object of type ``rabbit``, which of the
   following represent possible *properties* for this object? 

   a. size
   b. chew_flowers
   c. invade_garden
   d. age
   e. run
   f. color

.. Properties = a, d, f;