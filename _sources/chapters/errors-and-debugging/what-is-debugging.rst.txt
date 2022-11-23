What is Debugging?
==================

.. index:: ! debugging, ! bug

Programming is a complex process. Since it is done by humans, mistakes often
occur. Programming errors are called **bugs**, and the process of tracking bugs
down and fixing them is called **debugging**.

One popular story claims that in 1947, a dead moth caused a problem in one of
the first computers. The term *bug* has remained in use since, and it refers to
anything that prevents a program from working correctly. Wikipedia even has an
image of the supposed
`first bug <http://en.wikipedia.org/wiki/File:H96566k.jpg>`__.

.. index::
   single: error; syntax
   single: error; runtime
   single: error; logic

Three kinds of errors can occur in a program: **syntax errors**,
**runtime errors**, and **logic errors**. We will examine each type of error in
this chapter, explore some useful debugging strategies, and then review good
habits that help reduce errors.

Beginning Tips for Debugging
----------------------------

Debugging a program requires a different approach compared to writing the
original code. As you debug, think of yourself as a detective. Something has
gone wrong, and you must use clues, experience, intuition, trial and error, and
a logical approach to solve the problem.

Here are some suggestions to get you thinking about debugging:

#. Often, new coders find it tempting to blame errors on Python itself. However, it
   is far, far more likely that the *human* put the error into their own code.
#. Think critically about the code. Use any available tools to help find and
   fix the mistakes. Even senior developers make basic errors!
#. Learn how to use error messages and ``print`` statements to find clues.

Over time, you will sharpen your debugging skills and learn how to prevent bugs
from occurring in the first place.

Check Your Understanding
------------------------

.. admonition:: Question

   Debugging is:

   a. finding all the errors in the program.
   b. fixing all the errors in the program.
   c. finding and fixing all the errors in the program.

.. Answer = c


