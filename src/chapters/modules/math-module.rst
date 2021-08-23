The ``math`` Module
===================

The ``math`` module contains the kinds of functions you would find on your
calculator---like finding the **cosine** of an angle or the **square root** of
a number---as well as some constants like ``pi``.

Here are two items from the math module in action:

.. sourcecode:: python

   import math
   
   num = 30

   print(math.pi)
   print(math.sqrt(num))
   print(math.ceil(1.112))

**Console Output**

::

   3.141592653589793
   5.477225575051661
   2

``math.pi`` returns the first 16 digits of pi, ``math.sqrt()`` takes the square
root of a number, and ``math.ceil()`` rounds a decimal value UP to the next
whole number.

`W3 Schools <https://www.w3schools.com/python/module_math.asp>`__ provides a
complete list of the items in the ``math`` module.
