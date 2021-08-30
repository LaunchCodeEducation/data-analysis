Importing Modules
=================

One of the most important things to realize about modules is that they are
data *objects*. Just like a *string* is a collection of individual characters,
and a *list* is a collection of individual elements, *module objects* are
collections of data values and Python code blocks.

The ``import`` Keyword
----------------------

Before we can use any of the items stored in a module, we must import it. The
syntax for this is:

.. index:: ! import, dot notation

.. index::
   single: module; import

.. sourcecode:: Python

   import module_name

The **import** keyword tells Python to find the file called ``module_name`` and
make it available for use in the program. For example, the statement
``import string`` creates a new name, ``string``, which points to the module
where all of the string data and functions are stored.

.. admonition:: Tip

   Put all ``import`` statements in the very first lines of a program! This
   avoids runtime errors by importing all module items well before your code
   calls for them.

To use something stored in a module, we use **dot notation**, which joins the
name of the module with a variable or function name:

.. sourcecode:: Python

   module_name.variable_name              # Access the data assigned to variable_name
   module_name.function_name(arguments)   # Call function_name

For example, we have used the ``string`` module to access a list of all the
lowercase letters:

.. sourcecode:: Python
   :linenos:

   import string

   print(string.ascii_lowercase)    # Prints abcdefghijklmnopqrstuvwxyz

We can read this example of dot notation like this:

#. **Line 4** - In the ``string`` module, access the value for the variable
   ``ascii_lowercase``.

.. admonition:: Note

   In order to call a function stored in a module, we MUST know the name of
   that function. To access a data value stored in a module, we MUST know the
   variable name for that value.

Find the Names of Module Items
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. _dir-function:

.. index:: ! dir()

To figure out the names of all the items stored in a module, we could look them
up with a Google search. However, Python has a useful directory function,
``dir()``, that returns a list of names for everything stored in a module.

.. admonition:: Example

   .. sourcecode:: Python
      :linenos:

      import string

      print(dir(string))
   
   **Console Output**

   ::
   
      ['Formatter', 'Template', '_ChainMap', '_TemplateMetaclass', '__all__', '__builtins__',
      '__cached__', '__doc__', '__file__', '__loader__', '__name__',
      '__package__', '__spec__', '_re', '_sentinel_dict', '_string',
      'ascii_letters', 'ascii_lowercase', 'ascii_uppercase', 'capwords', 'digits',
      'hexdigits', 'octdigits', 'printable', 'punctuation', 'whitespace']

   To make this output easier to read, we can use a loop to print the list
   one element per line.

   .. replit:: py
      :slug: Print-Module-Contents
      :linenos:

      # Try running this code with different modules. Don't forget to change the module name in line 2 AND line 4!
      import string

      for item in dir(string):
         print(item)

.. admonition:: Tip

   From the list of names, skip those that begin with underscores ``__``. Using
   these is a more advanced skill, and we will focus on the other options for
   now.

The ``from`` Keyword
--------------------

.. index:: ! from

.. index::
   single: module; from

The ``import`` keyword makes every data value and function in a module
available for use. However, if we only need a few of the items from a module,
we can use the ``from`` keyword to import only those items.

.. sourcecode:: Python

   from module_name import item_name

``item_name`` refers to the specific function or variable that we want from the
module. If we want to import more than one item, we separate the names by
commas.

.. admonition:: Example

   Compare the syntax and results from the following imports:

   .. sourcecode:: Python
      :linenos:

      import string

      print(string.punctuation)
      print(string.ascii_letters)

   **Console Output**

   ::

      !"#$%&'()*+,-./:;<=>?@[\]^_`{|}~
      abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ

   Adding the ``from`` keyword:

   .. sourcecode:: Python
      :linenos:

      from string import punctuation

      print(punctuation)
      print(ascii_letters)

   **Console Output**

   ::

      !"#$%&'()*+,-./:;<=>?@[\]^_`{|}~
      Traceback (most recent call last):
      File "main.py", line 4, in <module>
         print(ascii_letters)
      NameError: name 'ascii_letters' is not defined

   Note that when we combine ``from ... import``, we do NOT need to use dot
   notation. We can call the variable or function directly by its name. Also note
   that ``ascii_letters`` results in a ``NameError``, because that data was not
   imported from the ``string`` module in line 1.

The ``as`` Keyword
------------------

.. index::
   single: module; as

Python gives us a way to rename the items we import by including the ``as``
keyword as part of the ``import`` statement:

.. sourcecode:: Python

   import module_name as new_name
   from module_name import item_name as new_name

Let's see how this works using the example above.

.. admonition:: Example

   Adding the ``as`` keyword:

   .. sourcecode:: Python
      :linenos:

      import string as str

      print(str.punctuation)
      print(str.ascii_letters)
   
   **Console Output**

   ::

      !"#$%&'()*+,-./:;<=>?@[\]^_`{|}~
      abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ

When using the ``as`` notation, notice the pattern is similar to that used in objects and classes.