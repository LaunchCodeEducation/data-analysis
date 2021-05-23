More On Variables
=================

The previous section covered creating, evaluating, and reassigning variables.
This section will cover some additional, more nuanced topics related to
variables.

Creating Constants
------------------

One of the key features of variables that we have discussed so far is their
ability to change value. We can create a variable with one value, and then
reassign it to another value.

.. sourcecode:: py
   :linenos:

   programmingLanguage = "JavaScript"
   programmingLanguage = "Python"

In some situations, we want to create variables that cannot change value. Many
programming languages, including Python, provide mechanisms for programmers
to make variables that are constant.

For example, suppose that we are writing a to-do list web application, named
"Get It Done!" The title of the application might appear in multiple places,
such as the title bar and the main page header.

.. figure:: figures/get-it-done.png
   :alt: A to-do list web application with application name in the title bar and main header.
   :height: 300px

   An example to-do list web application

We might store the name of our application in a variable so that it can be
referenced anywhere we want to display the application name.

.. sourcecode:: py

   appName = "Get It Done!"

This allows us to simply refer to the ``appName`` variable any time we want to
use it throughout our application. If we change the name of the application, we
only have to change one line of code, where the ``appName`` variable is
initialized.

One problem with this approach is that an unwitting programmer might change the
value of ``appName`` later in the code, leading to inconsistent references to
the application name. In other words, the title bar and main page header could
reference different names.

.. index:: ! constant

.. index::
   pair: variable; constant

Capitalizing the entire variable name ensures that the value of the variable cannot be changed later on.

.. sourcecode:: py

   APP_NAME = "Get It Done!"

Such an unchangeable variable is known as a **constant**, since its value is
just that.

How does Python prevent a programmer from changing the value of a constant?
Let's find out. Try running the following code in an editor. What happens?

.. admonition:: Example

   .. sourcecode:: py
      :linenos:

      APP_NAME = "Get It Done"
      APP_NAME = "Best TODO application Ever!"

   **Console Output**

   ::

      TypeError: Assignment to constant variable.

As we've seen with other examples---such as trying to declare a variable twice,
using incorrect syntax, or failing to enclose strings in quotes--- Python
prevents undesired code from executing by throwing an error.

Naming Variables
----------------

Valid Variable Names
^^^^^^^^^^^^^^^^^^^^

As you may have discovered already, not just any sequence of characters is a
valid variable name. For example, if we try to declare a variable with a name
containing a space, Python complains.

.. admonition:: Example

   .. sourcecode:: py

      application name = "Planning App"

   **Console Output**

   ::

      SyntaxError: Invalid syntax

Python provides a broad set of rules for naming variables, but there is no
reason to go beyond a few easy-to-remember guidelines:

.. index:: keywords

#. Use only the characters 0-9, a-z, A-Z, and underscore. In other words, do
   not use special characters or whitespace (space, tab, and so on).
#. Do not start a variable name with a number.
#. Do not use **keywords**, which are words reserved by Python for use by
   the language itself. We'll discuss these in detail in a moment.

Following these guidelines will prevent you from creating illegal variable
names. While this is important, we should also strive to create good variable
names.

Good Variable Names
^^^^^^^^^^^^^^^^^^^

Writing good code is about more than writing code that simply works and
accomplishes the task at-hand. It is also about writing code that can be read,
updated, and maintained as easily as possible. How to write code that achieves
these goals is a theme we will return to again and again.

One of the primary ways that code can be written poorly is by using bad
variable names. For example, consider the following program. While we haven't
introduced each of the components used here, you should be able to come to a
general understanding of the new components.

.. sourcecode:: py
   :linenos:

   x = 5
   Y = 3.14
   z = Y * x ** 2
   print(z)

Understanding what this program is trying to do is not obvious, to say the
least. The main problem is that the variable names ``x``, ``Y``, and ``z`` are
not descriptive. They don't tell us anything about what they represent, or how
they will be used.

.. pull-quote:: Variable names should be descriptive, providing context about the data they contain and how they will be used.

Let's look at an improved version of this program.

.. sourcecode:: py
   :linenos:

   radius_of_circle = 5
   PI = 3.14
   area_of_circle = PI * radius_of_circle ** 2
   print(area_of_circle)

With improved variable names, it now becomes clear that the program is calculating the area of a circle of radius 5.

.. admonition:: Tip
   
   When considering program readability, think about whether or not your code will make sense to another programmer. It is not enough for code to be readable by only the programmer that originally wrote it.

Keywords
--------

.. index:: ! keywords, ! reserved words

Our last note on naming variables has to do with a collection of words that are reserved for use by the Python language itself. Such words are called **keywords**, or **reserved words**.
Any word that is formally part of the Python language syntax is a keyword.

.. admonition:: Warning
   
   While ``print()`` may seem like a keyword, it is actually slightly different.
   It is actually a built-in name that is available by default in Python environments.
   Here is an `article <http://python-history.blogspot.com/2013/11/story-of-none-true-false.html>`_ by the Python language designer about the difference between built-in names and keywords if you are interested in learning more.

Attempting to use a keyword for anything other than it's intended use will result in an error.

.. admonition:: Tip
   
   Most code editors will highlight keywords in a different color than variables or other parts of your code. This serves as a visual cue that a given word is a keyword, and can help prevent mistakes.

We will not provide the full list of keywords at this time, but rather point them out as we learn about each of them. If you are curious, the `full list is available at W3Schools <https://www.w3schools.com/python/python_ref_keywords.asp>`_.

