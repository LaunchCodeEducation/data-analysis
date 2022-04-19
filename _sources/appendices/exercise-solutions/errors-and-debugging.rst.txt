
Exercises: Errors and Debugging Solutions
=========================================

Find and Fix Syntax Errors
--------------------------

.. _errors-and-debugging-exercise-solutions-part1:

#. **Error 1: Line 6**  Correct syntax should look like this:

   ::

      value = int(input("Enter an index value: "))
#. **Error 2: Line 9** Correct syntax should look like this

   ::

      if value > len(alphabet):
#. **Error 3: Line 12** Correct syntax should look like this:

   ::

       print("The letter at index {0} is '{1}'.".format(index, alphabet[index]))


:ref:`Back to Exercises<errors-and-debugging-exercises>`


Find and Fix Runtime Errors
---------------------------

.. _errors-and-debugging-exercise-solutions-part2:

#. **Error 1: Line 2**:  One option for correct syntax could be this:

   .. sourcecode:: python

      print("The last letter in '{0}' is '{1}'".format(word, word[-1]))

#. **Error 2: Line 5**:  What data type is user input?  What data type do you need?  Correct syntax could be this:

   .. sourcecode:: python

      second_num = int(input("Enter another whole number: "))

#. **Error 3: Line 10**:  Correct the variable name typo

   .. sourcecode:: python

      print("\tProduct = {0}".format(first_num * second_num))

:ref:`Back to Exercises<errors-and-debugging-exercises>`

Solve Logic Errors
------------------

#. **Part 1: Calculate a Percentage** 

   .. _errors-and-debugging-exercise-solutions-part3a:

   #. **Errors 1 and 2: Line 5**: Correct syntax could look like this:

      .. sourcecode:: python

         percentage = points_earned/points_possible * 100

   .. _errors-and-debugging-exercise-solutions-part3b:      

#. **Part 2: Convert a Student's Percentage into a Letter Grade**
   
   #. **Error 1: Lines 8, 10, 12, 14, & 16:** Fix the Letter Grades

   #. **Error 2: Lines 7, 9, 11, 13**:  Change ``>`` or ``<`` to include the value as well.   You could also update the order of percentage ranges, too.
      One solution could start like this:

      .. sourcecode:: python

         if score_percent >= 90:
            letter_grade = 'A'
         elif score_percent >= 80:
            letter_grade = "B"
         
         # rest of code...

.. _errors-and-debugging-exercise-solutions-part3c:

#. **Part 3: Validating a Username**:

   #. **Testing with** ``print()`` **statements**:  This is a demo, but syntax could look like this:

      .. sourcecode:: python

         if len(username) >= 5 and len(username) <= 10:  
            is_valid = True

         print(is_valid)  #testing with print is a easy way to check your work

   #. **Error 1: Lines 13-18**:  Correct syntax could look like this.

      .. sourcecode:: python

         for char in username: 
            if char in string.digits: 
               has_digit = True
            elif char not in string.ascii_letters:  
               is_valid = False
            # else:                 #else statement not needed
               # is_valid = True 
         
         print(is_valid)

:ref:`Back to Exercises<errors-and-debugging-exercises>`