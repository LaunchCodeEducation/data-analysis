More Object Details
===================

Objects allow us to collect related data and actions into one place. So far,
we have printed the values of properties one at a time using dot notation. What
if we try to print the object itself?

Printing Objects
----------------

The following code defines a ``Dog`` class with a small number of properties
and methods.

.. admonition:: Try It!

   Run the program to see how the ``print`` function displays the ``dog_1`` and
   ``dog_2`` objects.

   .. raw:: html

      <iframe height="700px" width="100%" src="https://repl.it/@launchcode/LCHS-Printing-Objects?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

Instead of giving us the information stored in each object, we see an output
similar to ``<__main__.Dog object at 0x7fa1a167c4c0>``. Despite the weird look,
this actually gives us some information:

#. The data type (an ``object`` of type ``Dog``).
#. A memory address, ``0x7fa1a167c4c0``, which differs between the two objects.

Usually, this format is not what we want to see when we print an object.
Fortunately, Python allows us to decide what an object should look like when it
gets printed.

The ``__str__`` Method
^^^^^^^^^^^^^^^^^^^^^^

.. index:: ! __str__

Every Python class includes a special method called ``__str__``. Notice that it
uses the same naming convention as the initializer: two underscores before and
after the name.

The ``__str__`` method is responsible for returning a string designed by the
programmer. This means that *we* get to choose what gets displayed when we
print our ``Dog`` objects.

In this case, let's format a string that includes the name and age of our pet.
Copy and paste this code into the editor above, making sure to indent each line
by the proper amount. Run the program to see the new output.

.. sourcecode:: python
   :lineno-start: 10

   def __str__(self):
      output = "Name of dog: {0}, Age of dog: {1} years"
      return output.format(self.name, self.age)

Note that the ``__str__`` method MUST create and return a string.

.. admonition:: Try It!

   Create your own return string in the ``__str__`` method. Feel free to
   include the ``is_cute`` value, or add and display new properties to the
   class.

Collect All Property Values
---------------------------

The ``__str__`` method allows us to print selected values for our object.
Python also gives us a way to quickly collect the property names and their
values from an object.

.. index:: vars()

We can use the function ``vars()`` to take an object and return a dictionary
that contains the properties as key/value paris.

.. _dog-class-complete:

.. admonition:: Try It!

   Run the program below and examine the output.

   .. raw:: html

      <iframe src="https://trinket.io/embed/python3/5fc55baeb8" width="100%" height="400" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>


   #. Line 14 creates a new ``Dog`` object and assigns it to ``dog_1``.
   #. ``vars(dog_1)`` returns a dictionary and assigns it to ``dog_data``. Each
      key in the dictionary matches one of the property names defined in the
      ``Dog`` class.
   #. Line 16 prints the ``dog_data`` dictionary.
   
   Note: We could easily iterate through the ``dog_data`` dictionary by keys,
   values, or both as we saw :ref:`here <dictionary-iteration>`.

Property and Method Names
^^^^^^^^^^^^^^^^^^^^^^^^^

Back in the Modules chapter, we learned how to use the
:ref:`dir() function <dir-function>` to collect and display the names for all
of the items in a module. We can use this function again for an object.

.. admonition:: Try It!

   #. Paste this code into the editor above, then run the program.

      .. sourcecode:: python
         :lineno-start: 18

         print("dog_1 items:")
         for item in dir(dog_1):
            print(item)
   
   #. ``dir(dog_1)`` returns a list of the names for each method and property
      defined in the ``Dog`` class. This includes special methods like
      ``__init__`` and ``__str__``.
   #. *Tip*: To skip the special names, add a conditional to the loop to check
      if the name contains a double underscore, ``__``.

      .. sourcecode:: python
         :lineno-start: 18

         print("dog_1 items:")
         for item in dir(dog_1):
            if '__' not in item:
               print(item)
