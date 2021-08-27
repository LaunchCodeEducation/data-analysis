Encapsulation
=============

.. index:: ! encapsulation

The other three pillars of object-oriented programming are polymorphism, encapsulation, and abstraction.
Let's turn to encapsulation.

**Encapsulation** is the bundling of related data and behaviors that operate on that data, usually with restricted access to internal, non-public data and behaviors.
In object-oriented programming, classes and objects allow us to encapsulate, or isolate, data and behavior to only the parts of our program to which they are relevant.
Restricting access allows us to expose only that data and behavior that we want others to be able to use.

There are three levels of access when it comes to **class members** (the properties or methods of a class):

#. ``public`` members are meant to be accessible inside and outside the class and by child classes. 
   Every class member we have work with so far would be considered a ``public`` member.
#. ``protected`` members are meant to be accessible inside the class and to child classes, but not outside the class. 
#. ``private`` members are meant to be accessed inside the class, not outside the class, and should not be accessed by any child class.

.. admonition:: Note

   While Python programmers can designate members as ``protected`` or ``private``, Python will still allow programmers to access members outside of classes.
   As you progress further in your career, you will find additional ways to designate members as ``protected`` or ``private`` that will help prevent access outside of a class.
   For now, focus on understanding *why* encapsulation is important!

``protected`` Members
---------------------

.. index:: ! protected member 

A ``protected`` **member** should not be accessed outside of a class, but can be used inside the class.
To designate a member as ``protected``, we need to add an underscore in front of the member's name.
Let's take a look at ``Person`` and ``Employee`` again.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      class Person:
         def __init__(self, name):
            self.name = name

         def print_name(self):
            print(self.name)

      class Employee(Person):
         def __init__(self, name, id_num, year):
            super().__init__(name)
            self._id_number = id_num
            self.year = year
            
         def print_info(self):
            print(self.name, self._id_number)

      jose = Employee("Jose", "C-10", 4)
      print(jose._id_number)
      jose.print_info()
   
   **Console Output**

   .. sourcecode:: bash

      C-10
      Jose C-10

In line 11, we put an underscore in front of ``id_number``.  We have designated ``id_number`` ``protected``. 
Now take a look at lines 18 and 19. 
If you run this code, it would run without any errors.
However, calling ``id_number`` outside of the class on line 18 is not appropriate.
Instead, we should follow line 20 and call the ``print_info()`` method to print the value of ``id_number``.

``private`` Members
-------------------

We have already seen ``private`` class members popping up in our code. 
``private`` members are designated with a double underscore, ``__``.

Let's expand our example above.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      class Person:
         def __init__(self, name, location):
            self.name = name
            self.__location = location

         def print_name(self):
            print(self.name)

         def print_data(self):
            print(self.__location)

      class Employee(Person):
         def __init__(self, name, id_num, year, location):
            super().__init__(name, location)
            self._id_number = id_num
            self.year = year

         def print_info(self):
            print(self.name, self._id_number, self.__location)

      jose = Employee("Jose", "C-10", 4, "St Louis")
      jose.print_data()       # this method is from the parent class

   
   **Console Output**

   ::

      St Louis

Through the hierachy of classes, a child class can access members of the parent class directly. 
As we did in the example above.  Line 4 initializes the property ``__location`` as ``private``.  
The the method ``print_data`` found in line 9 uses prints value of ``__location``

We are able to access the ``private`` property in the ``jose`` object by using the parent class method ``print_data`` in line 22.

However, if we wanted to have the child class initialize this property, it will fail.

.. admonition:: Example

   .. sourcecode:: python

      jose = Employee("Jose", "C-10", 4, "St Louis")
      jose.print_info()       # this method is from the child class

   **Console Output**

   :: 

      AttributeError: 'Employee' object has no attribute '_Employee__location'

While we can pass a value to ``__location``, we cannot access it with our  ``Employee`` class methods. 
There is some privacy here, but as we saw in the previous example, if you use the parent class methods you can still get to this value.

Check Your Understanding
------------------------

.. admonition:: Question

   For this question, refer to the code block below.

   .. sourcecode:: python
      :linenos:

      class Greeting:

         def __init__(self, name):
            self._name = "Jess"

         def say_hello(self):
            output = "Hello, {0}!"   
            print(output.format(self.name))

   What level of access has been given to ``name``?

   a. ``public``
   b. ``private``
   c. ``protected``

   .. ans: c


.. admonition:: Question

   Using the code block above, what will the output be when we add the following code:

   .. sourcecode:: python
      :lineno-start: 10


      belle.Greeting("Belle")
      belle.say_hello()

   a. An error will be thrown
   b. Hello, Jess!
   c. Hello, Belle

   .. ans: a