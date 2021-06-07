Why Create Functions?
=====================

Whew! You made it to the end of the chapter!

After plowing through all of the details for creating a function, you might ask
yourself, *Why would I ever want to do this?*

Good question! We have a few answers.

Functions Reduce Repetition
---------------------------

Like loops, functions help us keep our code DRY. When we need to repeat the
same basic task in multiple parts of a program, a function allows us to pack
the code for that task into a neat, reusable form.

Loops let us repeat the same task many times, but only in one part of a
program. Functions let us repeat the same task in different parts of a
program.

Functions Make Your Code More Readable
--------------------------------------

Writing a function to do a specific job allows us to put a name on that job.

Consider our ``is_palindrome`` example from the previous page:

.. sourcecode:: python
   :linenos:

   def reverse_string(a_string):
      letters_list = list(a_string)
      letters_list.reverse()
      return ''.join(letters_list)

   def is_palindrome(orig_string):
      return orig_string == reverse_string(orig_string)

The ``reverse_string`` function does exactly what its name says. It takes a
string and reverses the order of the characters.

The logic within ``is_palindrome`` is also clear. Line 7 tells us, *a string is
a palindrome if it is equal to its reverse*.

Functions Reduce Complexity
---------------------------

Large programs can be broken down into smaller parts using functions. Imagine a
car built out of a single, large piece of metal. When that car breaks down,
finding the problem will be difficult, and fixing it nearly impossible. The
mechanic would have to determine where the issue was, cut out the bad portion,
create a custom-made replacement part, and then weld it into place.

The repair complexity goes way down when a car is made up of lots of small
parts, each of which can be tested and replaced on its own. The same thing
happens with code. Small, simple chunks of code are easier to manage.

Functions Enable Code Sharing
-----------------------------

Writing a function to do one job makes it easy to reuse that code within a
program. It ALSO allows us to share that job across files and even different
projects.

Now that we coded ``reverse_string`` ONCE, we can reuse it whenever we need to
flip a string.

We will explore this idea in the :ref:`Modules chapter <modules-index>`.

Functions Save Millions of Lives Every Day
------------------------------------------

Okay, not really. However, functions are incredibly powerful tools. Ask a professional 
programmer if they could do their job without functions, and the answer will be an emphatic "NO!"

While functions may feel difficult to learn at first, repeated practice will
lead to mastery. Your work now will be worth it.
