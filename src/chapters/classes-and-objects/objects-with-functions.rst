Using Objects in Functions
==========================

Just like any other data type, we can send an object to a function as an input
value. We can also set up a function to create a new object and return it to the main
program.

.. admonition:: Example

   Assume we defined the same ``Dog`` class we used on the
   :ref:`previous page <dog-class-complete>`.

   .. sourcecode:: python
      :lineno-start: 14

      def make_puppy(parent_1, parent_2):
         puppy_name = parent_1.name[0] + parent_2.name[0]
         cuteness = parent_1.is_cute or parent_2.is_cute

         return Dog(puppy_name, 0, cuteness)

      dog_1 = Dog('Spot', 6, True)     # Create one Dog object
      dog_2 = Dog('Fleas', 2, False)   # Create another Dog object
      new_pet = make_puppy(dog_1, dog_2)  # Call make_puppy and return new Dog
      print(new_pet)

   **Console Output**

   ::

      Name of dog: SF, Age of dog: 0 years

   #. Lines 20 and 21 create two new ``Dog`` objects.
   #. Line 22 calls the ``make_puppy`` function and sends it ``dog_1`` and
      ``dog_2`` as arguments.
   #. Line 14 assigns the objects to the parameters ``parent_1`` and
      ``parent_2``.
   #. Line 15 combines the first letters of the parents' names to make the
      string for ``puppy_name``.
   #. Line 16 uses a boolean expression to decide if the puppy is cute.
   #. Line 18 creates and returns a new ``Dog`` object.
   #. Control returns to line 22, where the new object is assigned to
      ``new_pet``.

Object Scope
------------

Within a function, any change made to an object will change the object itself.

In the example above, adding the statement ``parent_1.name = "Fido"`` changes
the property value in the function AND outside of the function. If we
used ``print(dog_1.name)`` after calling ``make_puppy``, we would see
``Fido`` appear in the console instead of ``Spot``.

``parent_1`` is NOT a new ``Dog`` object. Instead, it is a new label that
points to the same set of data as ``dog_1``.

We saw similar behavior with both :ref:`lists <cloning-lists>` and
:ref:`dictionaries<dictionary-copy-example>`.

Check Your Understanding
------------------------

.. admonition:: Question

   Given ``bob = Pet()``, which of the following shows the object
   ``bob`` used as an *argument*?

   a. ``feed_pet(bob, lettuce)``
   b. ``def feed_pet(bob, lettuce):``
   c. ``return bob``

.. Answer = a

.. admonition:: Question

   Which of the following shows the object ``pet_name`` used as a *parameter*?

   a. ``label_habitat(pet_name, climate, habitat_size)``
   b. ``def label_habitat(pet_name, climate, habitat_size):``
   c. ``return pet_name``

.. Answer = b


