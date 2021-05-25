Loops With Conditions
=====================

In the :ref:`last chapter <conditionals>`, we learned how to use conditionals
to decide which block of code to run. In this chapter, we use loops to repeat a
set of statements multiple times.

You might wonder:

#. *Can I put a loop inside an if statement?*
#. *Can I put a conditional inside a loop?*

The answer to both of these questions is a definite, *YES!*

Repeating a Check
-----------------

Run the following code samples to see how each one behaves.

.. admonition:: Examples

   .. raw:: html

      <iframe height="450px" width="100%" src="https://repl.it/@launchcode/LCHS-Loops-with-Conditions-1?lite=true" scrolling="no" frameborder="yes" allowtransparency="true"></iframe>

   In this first loop, the text displayed in the console depends on whether the
   condition ``number%3 == 0`` returns ``True``. If ``number`` is evenly
   divisible by 3, then line 5 runs. Otherwise, line 7 runs.

   .. raw:: html
      
      <iframe height="450px" width="100%" src="https://repl.it/@launchcode/LCHS-Loops-with-Conditions-2?lite=true" scrolling="no" frameborder="yes" allowtransparency="true"></iframe>

   In the second loop, the condition ``char in 'aeiou'`` returns ``True`` if
   the value of ``char`` matches any part of the string. When this happens,
   ``num_vowels`` gets increased by 1 (line 6). ``Coding ROCKS!`` contains 2
   lowercase vowels, so line 6 only runs 2 times. For every other character in
   the string, the line gets skipped.

.. admonition:: Try It!

   How could you make the second program count both lowercase and uppercase
   vowels?

Looping ``if``
--------------

We can also place a loop inside any of the code blocks of an ``if/elif/else``
statement.

.. admonition:: Example

   .. sourcecode:: python
      :linenos:

      if condition:
         for var_name in range(value):
            # Loop body
      elif other_condition:
         for char in string:
            # Loop body
      else:
         for step in range(20):
            print("Python ROCKS!")

   Set up this way, only one of the three loops will run:

   #. IF ``condition`` is ``True``, the ``for`` loop starting on line 2 runs.
   #. IF ``condition`` is ``False`` and ``other_condition`` is ``True``, then
      the loop starting on line 5 runs.
   #. IF ``condition`` and ``other_condition`` both return ``False``, then
      ``Python ROCKS!`` gets printed 20 times by the last loop.

Placing a loop inside a conditional allows us to choose when the loop body
should run.
