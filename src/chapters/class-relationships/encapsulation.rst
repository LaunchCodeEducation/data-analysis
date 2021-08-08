Encapsulation
=============

.. index:: ! encapsulation

The other three pillars of object-oriented programming are polymorphism, encapsulation, and abstraction.
Let's turn to encapsulation.

**Encapsulation** is the bundling of related data and behaviors that operate on that data, usually with restricted access to internal, non-public data and behaviors.
In object-oriented programming, classes and objects allow us to encapsulate, or isolate, data and behavior to only the parts of our program to which they are relevant.
Restricting access allows us to expose only that data and behavior that we want others to be able to use.

There are three levels of access when it comes to class members:

#. **Public** members are meant to be accessible inside and outside the class and by child classes. In the last lesson, every property and method we created would be considered a public member.
#. **Protected** members are meant to be accessible inside the class and to child classes, but not outside the class. 
#. **Private** members are meant to be accessed inside the class, not outside the class, and should not be accessed by any base class.

.. admonition:: Note

   While Python programmers can designate members as protected or private, Python will still allow programmers to access members outside of classes.
   As you progress further in your career, you will find additional ways to designate members as protected or private that will help prevent access outside of a class.
   For now, focus on understanding why encapsulation is important!

Protected Members
-----------------

A protected member (property or method) should not be accessed outside of a class, but can be used inside the class.
To designate a member as protected, we need to add an underscore in front of the member's name.
Let's take a look at ``ParentClass`` and ``ChildClass``.

.. sourcecode:: python
   :linenos:

   class ParentClass:
      def __init__(self, a):
         self.a = a

      def important_method():
         print("This is an important method")

   class ChildClass(ParentClass):
      def __init__(self, a, b):
         super().__init__(self, a)
         self._b = b

      def print_info(self):
         print(self._b)


   x = ChildClass(2, 10)
   print(x.a)
   print(x._b)
   x.print_info()

Because we put an underscore in front of ``b``, we designated ``b`` as protected. Now take a look at lines 19 and 20. 
If you run this code, it would run without any errors.
However, calling ``b`` outside of the class on line 19 is not appropriate.
Instead, we should follow line 20 and call the ``print_info()`` method instead to print the value of ``b``.

Private Members
---------------

We have already seen private class members popping up in our code. Private members are designated with a double underscore.
Let's expand our example above.

.. sourcecode:: python
   :linenos:

   class ParentClass:
      def __init__(self, a, c):
         self.a = a
         self.__c = c

      def important_method():
         print("This is an important method")

   class ChildClass(ParentClass):
      def __init__(self, a, b, c):
         super().__init__(self, a, c)
         self._b = b

      def print_info(self):
         print(self._b)

While we can pass a value to ``__c``, we do not access it directly in ``ChildClass``.

Check Your Understanding
------------------------

.. admonition:: Question

   For this question, refer to the code block below.

   .. sourcecode:: python
      :linenos:

      class Greeting:

         def __init__(self):
            self.name = "Jess"

         def say_hello(self):
            output = "Hello {}!"   
            print(output.format(self.name))

   What level of access would you give ``name``?

   a. public
   b. private
   c. protected