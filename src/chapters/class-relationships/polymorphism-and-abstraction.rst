Polymorphism and Abstraction
============================

The final two pillars of OOP are polymorphism and abstraction. 

Polymorphism
------------

**Polymorphism** is an object-oriented mechanism that allows for objects of different types to be used in the same way.

Let's put this concept into practice. If we have a ``Rectangle`` class, we might have a child class called ``Square``.

.. sourcecode:: python
   :linenos:

   class Rectangle:
      def __init__(self, h, w):
         self.h = h
         self.w = w
      
      def area(self):
         return self.h * self.w

   class Square(Rectangle):
      def __init__(self, h, w):
         super().__init__(self, h, w)

      def area(self):
         return self.h ** 2

In both ``Square`` and ``Rectangle``, we have an ``area()`` function.
Since ``h`` and ``w`` have the same value for a square, we can find the area by squaring the value of ``h`` which is why we defined two separate functions under the same name.

Abstraction
-----------

The final pillar of OOP is abstraction. **Abstraction** is the process of separating data from implementation.
One way people accomplish this is by creating abstract classes.
An abstract class is designed to contain a shared set of behaviors that are passed down to child classes, but the abstract class is never instantiated itself.
If we look back at our cats example, a good abstract class would be something like ``Cat``. In this class, we would put a shared set of behaviors for all cats.
However, we don't want to instantiate a ``Cat`` object, because that is not very specific. Instead we would instantiate a ``HouseCat`` or ``Tiger`` object.

.. admonition:: Note

   We will not be coding an abstract class, however, if you want to learn how to make an abstract class, check out the `documentation <https://docs.python.org/3/library/abc.html>`_.

Check Your Understanding
------------------------

.. admonition:: Question

   If we were making an application for a school, which class would we want to make an abstract class?

   a. ``Teacher``
   b. ``Coach``
   c. ``Principal``
   d. ``Personnel``