What are Objects
================

A quick search of the web returns this fact:

   Python is an Object-Oriented Programming language.

Object-oriented programming (OOP) is a software design model that focuses on
the capabilities of *object types* instead of on things like individual
functions, loops, logic, etc. In this book, we won't get into the principles
behind OOP. However, we do need to take a closer look at the concept of
*objects*.

We have worked with objects many times already: turtle objects, string objects,
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

Another example of a Python object is a turtle.

.. sourcecode:: Python

   bob = turtle.Turtle()

Properties for the ``bob`` object include its color, speed, pen size, shape,
and location on the screen. Each of these bits of data tells us something about
the object. Methods include actions like ``.forward()`` and ``.circle()``.

Anything related to the appearance or behavior of a turtle on the screen is
included with every turtle object. We do not need to define a ``left()``
function to rotate a turtle. The code for that behavior is part of the object
itself.

Objects Organize Related Code
-----------------------------

All strings can use the same set of methods. However, if we try to use
``.upper()`` on an integer, list, or anything other than a string, Python
throws an error message. Similarly, the ``.forward()`` method only works with
turtle objects.

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
``.sort()`` makes sense for a list, but not for a turtle. Thus, every ``list``
object contains the code to rearrange the elements, but ``turtle`` objects do
not.

If we define a new ``elephant`` type of object, then that kind of object only
contains code to deal with elephant data and elephant behaviors. Any code not
related to elephants belongs somewhere else in our program.

Check Your Understanding
------------------------

.. admonition:: Question

   Assume we create an object of type ``rabbit`` in our code. Which of the
   following are *properties* for this kind of object, and which ones are
   *methods*? (Answer in your head before clicking each option).

   .. raw:: html

      <ol type="a">
         <li onclick="revealBinaryAnswer('A', true)">size <span id="A"></span></li>
         <li onclick="revealBinaryAnswer('B', false)">chew_flowers <span id="B"></span></li>
         <li onclick="revealBinaryAnswer('C', false)">invade_garden <span id="C"></span></li>
         <li onclick="revealBinaryAnswer('D', true)">age <span id="D"></span></li>
         <li onclick="revealBinaryAnswer('E', false)">run <span id="E"></span></li>
         <li onclick="revealBinaryAnswer('F', true)">color <span id="F"></span></li>
      </ol>

.. Properties = a, d, f; Methods = b, c, e.
