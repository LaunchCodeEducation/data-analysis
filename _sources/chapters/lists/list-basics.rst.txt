List Basics
===========

.. index:: ! list, ! element

The Python **list** data type is another example of an *ordered collection*.
Lists store data values, which are called **elements**. Just like with strings, each
element has its own index value. However, strings are ordered collections of *characters* and the elements of lists can be of any data type.

.. figure:: figures/list-diagram.png
   :alt: A label, languages, pointing to an array that contains "Python" at index 0, "C#" at index 1, "Java" at index 2, and "JavaScript" at index 3.

   This list contains four strings, and each value has its own index position.

Create a New List
-----------------

There are several ways to create a new list. The simplest is to enclose the
elements in square brackets ``[]``, with each element separated from the others
by commas.

.. admonition:: Example

   .. sourcecode:: Python
      :linenos:

      numbers = [5, 15, 15, 0, 25]
      strings = ['banana', 'broccoli', 'kale', 'applesauce']
      mixed_data = ["Hello", 42, True, 3.14, [-3, 48.5]]
      empty_list = []

.. index::
   single: list; empty

#. Line 1 assigns a list of five integers to the variable ``numbers``.
#. Line 2 assigns a list of four strings.
#. The elements of a list don’t have to be the same data type! The list in line
   3 contains a string, an integer, a boolean, a float, and another list.
#. Line 4 assigns a special list that contains no elements, called the
   **empty list**.

.. admonition:: Note

   A list within another list is said to be *nested*. We will explore this idea
   later in the chapter.

Accessing Elements
------------------

With strings, we accessed individual characters by using square brackets. With lists, we use square brackets to access list elements. The
integer or expression inside the brackets gives the *index* for the element we
want.

   Remember that index values start at 0.

Any integer (or an expression that returns a whole number) can be used as the
index. Negative index values identify elements from right-to-left, beginning
at ``-1`` for the last element in the list.

.. admonition:: Try It!

   Use index values to print out different elements from a list.

   #. Add at least three new elements to ``my_list``. Feel free to use values
      of the same data type or different data types.
   #. Note that line 4 prints the entire list (with brackets) to the console.
   #. Change the index value in line 5 to print different elements from
      ``my_list``. Be sure to try both positive and negative integers.
   #. Try using an expression (like ``len(my_list) - 2``) inside the brackets
      in line 5.
   #. What happens if you use an index value larger than the number of elements
      in the list?

   .. replit:: Python
      :slug: AccessingListElements
      :linenos:

      # Practice adding new elements to the list, and use bracket notation to print single elements from the list.
      my_list = ["Python"]

      print(my_list)
      print(my_list[0])

Check Your Understanding
------------------------

.. admonition:: Question

   List elements must all be the same data type.

   a. True
   b. False

.. Answer = b

.. admonition:: Question

   Identify the length of these two lists. (The answers list ``classes`` first,
   then ``teachers``).

   .. sourcecode:: Python
      :linenos:

      classes = ["Chemistry, US History, Intro To Coding"]
      teachers = ["Cortez", "Holmes", "Bracey"]

   a. 1 and 3
   b. 3 and 1
   c. 3 and 3
   d. 1 and 1

.. Answer = a

.. admonition:: Question

   Identify the output from the following statements:

   .. sourcecode:: Python
      :linenos:

      a_list = ["Hello", 42, True, 3.14]
      print(a_list[2])

   a. ``Hello``
   b. ``42``
   c. ``True``
   d. ``3.14``

.. Answer = c


