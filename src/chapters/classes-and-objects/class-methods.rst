Adding Methods to a Class
=========================

Recall that methods are the specific actions that objects can take. Methods can
either return a result, update property values, or both.

So far, we have learned how to set property values inside the ``constructor's __init__`` method. 
To assign methods to each new object, we must define them
inside the class, but outside of ``constructor``.

Return to the Class Design
--------------------------

:ref:`Earlier<brainstorm-properties>`, we made a list of property names that we wanted to include in our
``Cat`` class. We will repeat that process now, but this time we will record
ideas about what a ``Cat`` object should *do*.

.. _brainstorm-methods:

.. admonition:: Try It!

   Let's return to the :ref:`Cat class program we started desiging<define-new-class>`.

   Now we are going to add a few methods to our class.
   Take a moment to think of some cat behaviors that we want our objects to
   have.
   
   #. Some ideas to include could be ``make_noise()``, ``increase_age()``, ``eat()``, or ``ignore_humans()``.
   #. Include parentheses ``()`` with each name, but don't worry about setting
      parameters or coding anything yet.

Now that we have some possible ``Cat`` actions, let's see how to turn them into code.

Define a New Method
-------------------

To add a new method, the syntax is similar to a function definition:

.. sourcecode:: python
   :linenos:

   class ClassName:
      def __init__(self, parameters):
         # Assignment statements...

      def method_name(self, parameters):
         # Function code...

Note the following:

#. Methods are defined *within* the class, but are spearate from the properties.
#. The ``def`` keyword is used to define the new method.
#. ``method_name`` follows the same
   :ref:`naming conventions <function-naming-rules>` we use for functions.
#. All methods must include the ``self`` parameter, which appears first in the
   parentheses ``()``.
#. Additional parameters may or may not be used, depending on what we need the
   method to do.

Add a Method to the ``Cat`` Class
---------------------------------

As mentioned above, methods can return a value or change a property value.
Let's update our ``Cat`` class to include ``increase_age()``. This method will
take the ``age`` property of a ``Cat`` object and make it larger.

.. admonition:: Note

   This walkthrough is using a new replit codebase.  
   If you have your ``Cat`` program from before, you can make the same updates to your existing code.
   If using your own code, be aware that your line numbers won't match up with the directions, 
   but you should still be able to accomplish all the tasks in the directions. 

.. admonition:: Try It!

   On line 6, we define a method to increase a cat's age by 1 year. Note the
   following:

   #. The method requires no parameters other than ``self``.
   #. The statement ``self.age += 1`` updates the ``age`` property by 1 unit.
   #. No return statement is needed for this method. It takes the current value
      of the ``age`` property and increases it by 1.

   .. replit:: python
      :slug: Creating_Classes-02-A
      :linenos:

      class Cat:
         def __init__(self, name, age):
            self.name = name
            self.age = age

         def increase_age(self):
            self.age += 1

   Now do the following:

   #. On line 9, create a new cat object with the statement
      ``cat_1 = Cat('Whiskers', 3)``.
   #. Print the value for ``cat_1.age``.
   #. On line 12, call the method with the statement ``cat_1.increase_age()``.
      No arguments are needed inside the parentheses ``()``. The code
      automatically assigns ``cat_1`` to ``self``.
   #. Print ``cat_1.age`` again to see its new value.

As written, the ``increase_age()`` method only increases the value of ``age``
by 1 year. Let's modify the method to add a user specified amount of years.

#. In the editor above, add another parameter in line 6. Call this variable
   ``increase``, and assign it a default value of ``1``.
#. Change line 7 to be ``self.age += increase``.
#. On line 12, include an argument inside the parentheses. Run the program
   several times using different values to check your code. Also, try running
   the code without placing an argument in the method call.

OK! The ``Cat`` class now has a method. All objects made from the class will be
able to call ``increase_age()``.

Return Values
-------------

Next, let's add a method that *returns* a value when called. We will name it
``make_noise()``, and it will return the sound our cat makes based on its
current mood.

.. _add-more-cat-methods:

.. admonition:: Try It!

   Examine the code below, then run the program.

   .. replit:: python
      :slug: ClassMethods03
      :linenos:

      class Cat:
         def __init__(self, name, age):
            self.name = name
            self.age = age
         
         def increase_age(self, increase = 1):
            self.age += increase
         
         def make_noise(self, mood):
            if mood.lower() == 'hungry':
               noise = "Meow!"
            elif mood.lower() == 'angry':
               noise = "HISS!"
            else:
               noise = "Purr!"
            
            return noise

      cat_1 = Cat('Garfield', 42)
      cat_2 = Cat('Socks', 5)

      cat_1.make_noise('hungry')
      cat_2.make_noise('happy')

   Notice that no output appears in the console when we run the program. This
   is because the code contains no ``print`` statements! The ``make_noise()``
   method *returns* a value. In order for us to see it, we need to tell the
   program to display the data.

   #. Put ``cat_1.make_noise('hungry')`` inside a ``print`` statement and then
      run the program. ``Meow!`` should appear in the console.
   #. On line 23, ``cat_2.make_noise('happy')`` returns a value. Assign that
      value to a new variable, then print the variable. ``Purr!`` should now
      show up in the console.
   #. Try changing the arguments inside the method calls. How does the method
      decide which noise to return?
   #. Add another ``elif`` block to the method code to deal with one more
      option for ``mood``. Test your code by running the program and sending the
      new mood value to the method.

When Python comes to a method call, it evaluates that expression. If the method
returns a value, Python can then work with that result.

Add Your Own Method
-------------------

You started this page by listing your ideas for possible ``Cat`` methods. Take
another look at :ref:`your list <brainstorm-methods>` and choose one item.

In the editor from the :ref:`Return Values section <add-more-cat-methods>`:

#. Code your choice as the third method inside the ``Cat`` class. Your new
   method can either update a property value, return a value, or do both.
#. At the bottom of the editor, call your new method on ``cat_1`` and ``cat_2``
   to make sure it works as expected.

Improving ``make_noise()``
--------------------------

Notice that we must provide an argument for a cat's mood when we call
``make_noise()``. However, *mood* seems like a good property to include with
our object.

If we add a ``mood`` property to our ``Cat`` class, we can use it in the method
code instead of setting up a new parameter.

.. sourcecode:: python
   :linenos:

   class Cat:
      def __init__(self, name, age, mood):
         self.name = name
         self.age = age
         self.mood = mood.lower()

      def increase_age(self, increase = 1):
         self.age += increase
      
      def make_noise(self):
         if self.mood == 'hungry':
            noise = "Meow!"
         elif self.mood == 'angry':
            noise = "HISS!"
         else:
            noise = "Purr!"
         
         return noise

#. On line 5, we define the ``mood`` property and assign it a value when a new
   ``Cat`` object is created. By including the ``.lower()`` string method here,
   we can remove it from the conditionals in ``make_noise()``. 
#. Inside the ``make_noise()`` code block, ``self.mood`` accesses the current
   value of the property and compares it to the different options.
#. If we change ``mood`` in a different part of our code (say, by feeding or
   petting our cat), we do not need to worry about sending in the new value
   when we call the method. Any changes to the property are immediately
   available inside the method.

Check Your Understanding
------------------------

.. admonition:: Question

   What is printed with this program runs?

   .. sourcecode:: python
      :linenos:

      class Plant:
         def __init__(self, type, height, soil):
            self.type = type
            self.height = height
            self.soil = soil

         def grow(self, watered):
            if watered and self.soil == 'dry':
               self.height = self.height + 2
               self.soil = 'wet'
               return "Your plant is healthy."
            elif watered and self.soil == 'wet':
               return "You're killing your plant!"
            elif self.soil == 'wet':
               self.height = self.height + 1
               self.soil = 'dry'
               return "Water your plant soon."
            else:
               return "You killed your plant."

      fern = Plant('Fern', 5, 'wet')
      fern.grow(True)
      print(fern.height)

   a. 5
   b. 6
   c. Your plant is healthy.
   d. You're killing your plant!

.. Answer = a

.. admonition:: Question

   Given ``sticky = Plant('Bamboo', 100, 'dry')``, what would be the value for
   ``height`` after the following statements run?

   .. sourcecode:: python
      :lineno-start: 22

      sticky.grow(True)
      sticky.grow(False)
      sticky.grow(True)
      sticky.grow(True)

   a. 108
   b. 106
   c. 105
   d. 104

.. Answer = c