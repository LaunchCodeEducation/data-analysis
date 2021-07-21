Adding Methods to a Class
=========================

Recall that methods are the specific actions that objects can take. Methods can
either return a result, update property values, or both.

So far, we have learned how to set property values inside the initialization
method, ``__init__``. To assign methods to each new object, we must define them
inside the class, but outside of ``__init__``.

Return to the Class Design
--------------------------

Earlier, we made a list of property names that we wanted to include in our
``Cat`` class. We will repeat that process now, but this time we will record
ideas about what a ``Cat`` object should *do*.

.. _brainstorm-methods:

.. admonition:: Try It!

   If you saved your work from the :ref:`Design a New Class <brainstorm-properties>`
   section, you should see your list of properties in the editor below. If not,
   don't worry! You can still record your method ideas.

   .. raw:: html

      <iframe src="https://trinket.io/embed/python/15b49a8e24?toggleCode=true&runOption=run" width="100%" height="350" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>
   
   Take a moment to think of some cat behaviors that we want our objects to
   have.
   
   #. Below the last triple quote line (``'''``) add a new comment:

      .. sourcecode:: python

         # Make a list of methods that describe cat behaviors:

   #. On the next line, add another set of triple quotes (``'''``). Below this,
      type some possible method names. Examples include ``make_noise()``,
      ``increase_age()``, ``eat()``, or ``ignore_humans()``.
   #. Include parentheses ``()`` with each name, but don't worry about setting
      parameters or coding anything yet.
   #. Finish your list with another triple quote line.

   Add at least three method names to the editor, but don't limit yourself to
   the given examples. Include your own ideas!

.. admonition:: Note

   Why :ref:`triple quotes <quote-reminder>`? This syntax allows us to
   break a single string over multiple lines in the editor. We use them
   here to record our ideas but keep the editor from flagging an error.

Now that we have some possible ``Cat`` actions, let's see how to turn them into
code.

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

.. admonition:: Try It!

   On line 6, we define a method to increase a cat's age by 1 year. Note the
   following:

   #. The method requires no parameters other than ``self``.
   #. The statement ``self.age += 1`` updates the ``age`` property by 1 unit.
   #. No return statement is needed for this method. It takes the current value
      of the ``age`` property and increases it by 1.

   .. raw:: html

      <iframe src="https://trinket.io/embed/python3/6431d81de9" width="100%" height="300" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

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

   .. raw:: html

      <iframe src="https://trinket.io/embed/python3/becfc4eae4" width="100%" height="500" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

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

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, true)"> 5</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> 6</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> Your plant is healthy.</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> You're killing your plant!</li>
      </ol>
      <p id="Q1"></p>

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

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> 108</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> 106</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, true)"> 105</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> 104</li>
      </ol>
      <p id="Q2"></p>

.. Answer = c