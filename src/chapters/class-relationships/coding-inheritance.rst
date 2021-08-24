Putting Inheritance into Practice
==================================

Now that we know what inheritance is, let's look at how we code parent and child classes.

When setting up parent and child classes, we may first think about what behaviors belong in the parent class and which are specific to child classes.
Let's say we create a class called ``ParentClass``:

.. TODO: update code; source: https://www.w3schools.com/python/python_inheritance.asp

.. sourcecode:: python
   :linenos:

   class ParentClass:
      def __init__(self, a):
         self.a = a

      def important_method():
         print("This is an important method")

If we do not want to add any additional properties and/or methods to a child class, we will use the ``pass`` keyword when setting up the child class.

.. sourcecode:: python
   :linenos:

   class ChildClass(ParentClass):
      pass

``ChildClass`` is now set up to inherit all the properties and methods of ``ParentClass``. This means we could call ``important_method()`` if we needed to.

.. sourcecode:: python
   :linenos:

   x = ChildClass(5)
   x.important_method()

In most cases, you may want to add an additional property or method to the child class. In this case, first we need to set up the constructor for the child class with an additional property, ``b``.

.. sourcecode:: python
   :linenos:

   class ChildClass(ParentClass):
      def __init__(self, a, b):
         ParentClass.__init__(self, a)
         self.b = b

We can also use the ``super()`` function to pass the parent class's constructor to the child class.

.. sourcecode:: python
   :linenos:

   class ChildClass(ParentClass):
      def __init__(self, a, b):
         super().__init__(a)
         self.b = b

Cats, Tigers, and Housecats, Oh My!
-----------------------------------

.. TODO: update code, create replit, and short walkthrough for students

With the general syntax down, let's code some cat classes. On the previous page, we talked about how we might use inheritance to set up some cat classes.
Let's take a look at how we could use ``super()`` to set up our cat classes.

.. sourcecode:: python
   :linenos:

   class Felidae:
      def __init__(self):
         self.claws = "retractable"

   class Panthera(Felidae):
      def __init__(self):
         super().__init__(self)
         self.roar = "loud"

   class Tiger(Panthera):
      def __init__(self):
         super().__init__(self)
         self.has_stripes = True

   class Felis(Felidae):
      def __init__(self):
         super().__init__(self)
         self.pupils = "vertical"
   
   class Housecat(Felis):
      def __init__(self):
         super().__init__(self)
         self.personality = "judgemental"

Check Your Understanding
------------------------

.. admonition:: Question

   If you had to create classes for a *wolf*, the *canis* genus, and the *carnivora* order, which statement is TRUE about the order of inheritance?

   a. ``Wolf`` and ``Canis`` are parent classes to ``Carnivora``.
   b. ``Wolf`` is a child class of ``Canis`` and a parent class to ``Carnivora``.
   c. ``Wolf`` is child class of ``Canis``, and ``Canis`` is a child class of ``Carnivora``.
   d. ``Wolf`` is child class of ``Canis``, and ``Canis`` is a parent class of ``Carnivora``.

