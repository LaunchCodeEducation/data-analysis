Putting Inheritance into Practice
==================================

Now that we know what inheritance is, let's look at how we code parent and child classes.

.. admonition:: Tip

   Fun fact: A parent class may also be referred to as the **base** class or 
   **super** class while child classes may be referred to as **derived** classes, **subclasses** or **subtypes**. 

Design Your Classes
-------------------

As you think about classes and inheritance, it's important to remember how inheritance works.  
A child class derives, extends or inherits a parent class.  

When setting up parent and child classes, 
we may first think about what behaviors belong in the parent class and which are specific to child classes.
Let's say we create a class called ``Person`` that takes a single arguement and contains a single method.

.. admonition:: Example:

   .. sourcecode:: python
      :linenos:

      # This is the parent class
      class Person:
         def __init__(self, name):
            self.name = name
         
         def printname(self):
            print(self.name)"

      naomi = Person("Naomi")
      namoi.printname()

   **Console Output**

   .. sourcecode:: python

      Naomi

Line 9, we create a new ``Person`` object and pass it a value of "Naomi".  In line 10, we call the ``printname`` 
method, using the value we initially provided.  The console then prints "Naomi" to the console.  So far our 
``Person`` class is working.  Let's extend it to another class called ``Employee``.

As we define ``Employee`` we pass it the ``Person`` class in parentheses (see line 1 below).
If we do not want to add any additional properties and/or methods 
to a child class, we will use the ``pass`` keyword when setting up the child class.
``pass`` is a null statement often used as a placeholder for code.  
In this example, it is allowing us to create a new child class without any ``constructors`` or methods.

.. admonition:: Example:

   .. sourcecode:: python
      :linenos:

      class Employee(Person):
         pass

      # let's test if our inheritance syntax is sound
      xin = Employee("Xin")
      xin.printname()

   **Console Output**

   .. sourcecode:: python 

      Xin

When we call the ``Employee`` we see the output above.  
Our initial syntax is functional, and ``Employee`` is now set 
up to inherit all or selected the properties and methods of ``Person``. 

However, in most cases, you may want to add an additional property or method to the child class. 

Inheritance Syntax
------------------

If so, we first need to set up the ``constructor`` for the child class.  
The syntax is the same as you would for any class.  
Be sure to include any properties you need in the initial ``constructor``.
In this example, we are going to add ``id_num`` and ``year`` parameters.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      class Employee(Person):
	      def __init__(self, name, id_num, year):

      xin = Employee("Xin")
      xin.printname()
         
If we were to run our code now, it codes throws an AttributeError. 
In line 1, we have to proper syntax for inheritance, 
but within our class there are no instructions for how to use the parent class.
We need to add code to let our child class know what to use from the parent class.

The ``super()`` Function
^^^^^^^^^^^^^^^^^^^^^^^^

The ``super()`` function pulls in the ``constructor`` from a parent class to a child class.  
This provides access to all properties and methods in the parent class. 

.. admonition:: Note

   If you recall, parent classes are also referred to as super classes, hence ``super()``.

In line 9 we called ``super().__init__(name)``.  ``name`` is the parameter from the ``Person`` ``constructor``.
When using this syntax, you need to provide the parameters from the parent class's ``constructor``.  All of them except ``self``.  

Whatever parameters the parent class extends to the child class must be in the child class's constructor.

.. admonition:: Example

   .. replit:: python
      :slug: InheritanceSuperSyntax
      :linenos:

      class Person:
         def __init__(self, name):
            self.name = name
         def printname(self):
            print(self.name)

      class Employee(Person):
         def __init__(self, name, id_num, year):
            super().__init__(name)                  
            self.id_number = id_num                
            self.years_employeed = year         
         
         def print_id_num(self):
            print(self.id_number)
 
In line 9 the ``constructor`` from the ``Person`` class is added to the definition of ``Employee`` using ``super()``.  
``Person`` has one parameter, ``name`` that it is extending to ``Employee``.  Due to this extension, ``name`` must be added
to the ``Employee`` ``constructor``.

Calling the Parent Constuctor Directly
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

We can also use the directly pass the parent class's ``constructor`` to the child class.
In this instance, there are no parentheses after the ``Person`` and we add ``self`` to the parameter list.
Output will be the same, it's just a matter of preference.

.. admonition:: Example

   .. sourcecode:: python
      :lineno-start: 7
      
      class Employee(Person):
         def __init__(self, name, id_num, year)       
            Person.__init__(self, name)            




Check Your Understanding
------------------------

.. admonition:: Question

   If you had to create classes for a *wolf*, the *canis* genus, and the *carnivora* order, which statement is TRUE about the order of inheritance?

   a. ``Wolf`` and ``Canis`` are parent classes to ``Carnivora``.
   b. ``Wolf`` is a child class of ``Canis`` and a parent class to ``Carnivora``.
   c. ``Wolf`` is child class of ``Canis``, and ``Canis`` is a child class of ``Carnivora``.
   d. ``Wolf`` is child class of ``Canis``, and ``Canis`` is a parent class of ``Carnivora``.




.. admonition:: Question

   Use the following code block to answer the next two questions.

   .. replit:: python
      :slug: Cat-Inheritance
      :linenos:

      class Felidae:
         def __init__(self):
            self.claws = "retractable"

      class Panthera(Felidae):
         def __init__(self):
            super().__init__()
            self.roar = "loud"

      class Tiger(Panthera):
         def __init__(self):
            super().__init__()
            self.has_stripes = True

      class Felis(Felidae):
         def __init__(self):
            super().__init__()
            self.pupils = "vertical"

      class Housecat(Felis):
         def __init__(self):
            Felis.__init__(self)
            self.personality = "judgemental"

      lion = Felidae()   
      leopard = Panthera()
      tiger = Tiger()
      sand_cat = Felis()
      tabby_cat = Housecat()
         
.. admonition:: Question

   Which objects listed below have access to the ``pupils`` attribute of the Felis class?

   a. ``sand_cat`` only
   b. ``sand_cat``, ``tiger``, and ``tabby_cat``
   c. ``sand_cat`` and ``tabby_cat``
   d. ``sand_cat``, ``lion``, ``tiger``

   .. ans: c

.. admonition:: Question

   #. What is the order of inheritance of the ``Housecat`` class?  (moving from child to parent)

   a. ``Housecat``, ``Felis``, ``Tiger``
   b. ``Housecat``, ``Felis``, ``Felidae``
   c. ``Housecat``, ``Felis``, ``Panthera``
   d. ``Housecat``, ``Felidae``, ``Felis``

   .. ans: b



