Functions Calling Other Functions
=================================

Once we define a function, we can call it on its own, as part of a conditional,
or from inside of a loop.

.. admonition:: Example

   .. sourcecode:: Python
      :linenos:

      def double_number(num):
         return num*2

      integer = 8
      my_function(integer)

      if integer > 5:
         my_function(integer)
      
      for number in range(10):
         my_function(number)

Even better, we can call one function from INSIDE another function.

To demonstrate, let's consider a specific example.

Palindrome Checker
------------------

A **palindrome** refers to a word that is spelled the same backwards and
forwards. Two examples are "mom" and "level".

Let's write a :ref:`boolean function <boolean-function>` to check if a word is a
palindrome.

We will call a palindrome a string that is identical to its reverse. This means
we can test for palindromes by taking a string, reversing it, and then
comparing the reversed string to the original. If the two are equal, we have a
palindrome.

Since we want to compare a string to its reverse, we'll need a function that flips a string.

The ``reverse_string`` Function
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Let's write a function that, given a string, returns its reverse.

One approach is to use the list method ``reverse()`` in combination with
``list()`` and ``join()`` (this was covered in the
:ref:`split and join section <list_reverse-a-string>`).

.. _reverse_func:

.. sourcecode:: python
   :linenos:

   def reverse_string(a_string):
      letters_list = list(a_string)
      letters_list.reverse()
      return ''.join(letters_list)

Let's break down the steps carried out by this function:

#. **Turn the string into a list of characters.** We call ``list(a_string)``,
   which returns a list of the individual characters that make up the string.
#. **Reverse the list of characters.** To do this, we use the built-in list
   method ``reverse()``.
#. **Join the reversed character list into a string.** We call
   ``''.join(letters_list)``. Joining with the empty string combines all of the
   list elements together into a single string with no spaces in between.

.. _palindrome-function:

The ``is_palindrome`` Function
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Using our ``reverse_string`` function, we can now create our palindrome
checker. Our approach will be to take the string argument, reverse it, and then
compare the reversed string to the original.

.. admonition:: Try It!

   Does the ``is_palindrome`` function work? See for yourself by adding this
   code:

   .. sourcecode:: python
      :lineno-start: 9

      print(is_palindrome(string_value))

   Here are a few strings to try:

   #. ``'dad'``      (True)
   #. ``'Mom'``      (False)
   #. ``'radar'``    (True)
   #. ``'taco cat'`` (False)

   .. raw:: html

      <iframe height="550px" width="100%" src="https://repl.it/@launchcode/Palindrome-Checker?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>


.. admonition:: Try It!

   Currently, the code does not count ``'Mom'`` as a palindrome because
   ``'Mom'`` is not the same string as ``'moM'``. Try making the
   ``is_palindrome`` function *case-insensitive* by using the ``.lower()``
   string method.

   Case-insensitive means that both ``mom`` and ``Mom`` return ``True`` for
   being palindromes.

Functions Should Do Exactly One Thing
-------------------------------------

When writing a function, we should pay attention to its size. Functions work best when they are
small and do only one thing.

This idea is easier to say than to put into practice. For example, what if we
wrote ``is_palindrome`` without putting the ``reverse_sting`` code in a
separate function?

.. sourcecode:: python
   :linenos:

   def is_palindrome(orig_string):
      letters_list = list(orig_string)
      letters_list.reverse()
      rev_string = ''.join(letters_list)

      return orig_string == rev_string

This function is still short, which is good. However, it does two separate
jobs---it reverses a string *and* decides if that string is a palindrome.

Making a palindrome checker with one function vs. two might not seem like a big
deal now. But what if we need to reverse a string for some other reason? We cannot
use the combined ``is_palindrome`` function, since it only returns ``True`` or
``False``. If we need to flip the order of a string, then we should write a
function that just DOES THAT ONE JOB.

Consider the ``make_sandwich`` function from an
:ref:`earlier section <sandwich-function>`. What if we wanted to expand our
program to not only make a sandwich, but also to pour a drink. It would be a
bad idea to write one function to do both (``make_sandwich_and_pour_drink``).
What if a customer wants only one thing---a sandwich or a drink?

A much better solution would look like this:

.. sourcecode:: python
   :linenos:

   def make_sandwich( parameters ):
      # make the sandwich

   def pour_drink( parameters ):
      # pour the drink

   def make_lunch( parameters ):
      make_sandwich( sand_arguments )
      pour_drink( drink_arguments )

Why is this better? First, smaller functions are easier to debug. Also, by
assigning single jobs to separate functions, we make our code easier to read
and more reusable.

Looking at the ``make_lunch`` function, it is very clear what is going on.
It makes a sandwich first, and then it pours a drink.

If the ``make_lunch`` function held all of the code needed to do *both* tasks,
there would be no clear separation between one job and the other.
