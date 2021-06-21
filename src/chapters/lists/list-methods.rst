.. _list-methods:

List Methods
============

.. index::
   single: list; methods

As with strings, Python provides us with useful **methods** for lists. These
methods will either *change* an existing list, *return* information about the
list, or *create and return* a new list.

Common List Methods
--------------------

Here is a sample of the most frequently used list methods. More complete lists
can be found here:

#. `W3Schools <https://www.w3schools.com/python/python_ref_list.asp>`__
#. `Python.org <https://docs.python.org/3/tutorial/datastructures.html>`__

To see detailed examples for a particular method, click on its name.

.. list-table:: Methods That Return Information About The List
   :header-rows: 1

   * - Method
     - Syntax
     - Description
   * - :ref:`count <list-count-examples>`
     - ``list_name.count(value)``
     - Returns the number of elements in the list that match ``value``.
   * - :ref:`index <list-index-examples>`
     - ``list_name.index(value)``
     - Returns the index of the FIRST occurrence of ``value`` in the list. If
       the value is not in the list, Python throws an error.

.. list-table:: Methods That Rearrange The Entries In The list
   :header-rows: 1

   * - Method
     - Syntax
     - Description
   * - :ref:`reverse <list-reverse-example>`
     - ``list_name.reverse()``
     - Reverses the order of the elements in a list.
   * - :ref:`sort <list-sort-examples>`
     - ``list_name.sort()``
     - Arranges the elements of a list into increasing or decreasing order.

.. list-table:: Methods That Add Or Remove Entries From A List
   :header-rows: 1

   * - Method
     - Syntax
     - Description
   * - :ref:`append <list-append-examples>`
     - ``list_name.append(value)``
     - Adds ``value`` to the end of the list.
   * - :ref:`clear <list-clear-examples>`
     - ``list_name.clear()``
     - Removes all elements from a list.
   * - :ref:`insert <list-insert-examples>`
     - ``list_name.insert(index, value)``
     - Adds ``value`` at the specified ``index`` in the list. This pushes
       existing elements further down the list.
   * - :ref:`pop <list-pop-examples>`
     - ``list_name.pop(index)``
     - Removes and returns the element at the given ``index`` value. If no
       ``index`` is provided, the last element in the list gets removed.
   * - :ref:`remove <list-remove-examples>`
     - ``list_name.remove(value)``
     - Removes the FIRST element in a list that matches ``value``.

.. list-table:: Methods That Create New Lists
   :header-rows: 1

   * - Method
     - Syntax
     - Description
   * - :ref:`join <list-join-examples>`
     - ``'connecter'.join(list_name)``
     - Combines all the elements of a list into a string.
   * - :ref:`split <string-split-examples>`
     - ``'string'.split('delimiter')``
     - Divides a string into smaller pieces, which are stored as separate
       elements in a new list.
   * - :ref:`list <list-function>`
     - ``list(collection)``
     - This is a function rather than a method, and it behaves similarly to
       data conversion functions like ``int()`` and ``str()``. The ``list()``
       function tries to convert the whatever is inside the ``()`` into a list.

Check Your Understanding
------------------------

As you answer these questions, follow the links in the table above as needed.

.. admonition:: Question

   What is printed by the following code?

   .. sourcecode:: js
      :linenos:

      string_list = ['coder', 'Tech', '47', '23', '350']
      string_list.sort()
      print(string_list)

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> ['350', '23', '47', 'Tech', 'coder']</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> ['coder', 'Tech', '23', '47', '350']</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> ['23', '47', '350', 'coder', 'Tech']</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, true)"> ['23', '350', '47', 'Tech', 'coder']</li>
      </ol>
      <p id="Q1"></p>

.. Answer = d

.. admonition:: Question

   Which statement converts the string ``text = 'Coding students rock!'`` into
   the list ``['Coding', 'students', 'rock!']``?

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">text.join()</span></li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, true)"> <span style="color:#419f6a; font-weight: bold">text.split()</span></li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">text.join("")</span></li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">text.split("")</span></li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> <span style="color:#419f6a; font-weight: bold">list(text)</span></li>
      </ol>
      <p id="Q2"></p>

.. Answer = b

.. admonition:: Question

   What is printed by the following program?

   .. sourcecode:: python
      :linenos:

      grocery_bag = ['bananas', 'apples', 'edamame', 'chips', 'cucumbers', 'milk', 'cheese']
      selected_items = []

      selected_items = grocery_bag[2:5]
      selected_items.sort()
      print(selected_items)

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, true)"> ['chips', 'cucumbers', 'edamame']</li>
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, false)"> ['chips', 'cucumbers', 'edamame', 'milk']</li>
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, false)"> ['apples', 'chips', 'edamame']</li>
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, false)"> ['apples', 'chips', 'cucumbers', 'edamame']</li>
      </ol>
      <p id="Q3"></p>

.. Answer = a

.. admonition:: Question

   What is printed by the following program?

   .. sourcecode:: python
      :linenos:

      a_list = [4, 2, 8, 6, 5]
      a_list.append(True)
      a_list.append(False)
      print(a_list)

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q4" autocomplete="off" onclick="evaluateMC(name, false)"> [4, 2, 8, 6, 5, False, True]</li>
         <li><input type="radio" name="Q4" autocomplete="off" onclick="evaluateMC(name, true)"> [4, 2, 8, 6, 5, True, False]</li>
         <li><input type="radio" name="Q4" autocomplete="off" onclick="evaluateMC(name, false)"> [True, False, 4, 2, 8, 6, 5]</li>
      </ol>
      <p id="Q4"></p>

.. Answer = b

.. admonition:: Question

   What is printed by the following program?

   .. sourcecode:: python
      :linenos:

      a_list = [4, 2, 8, 6, 5]
      a_list.insert(2, True)
      a_list.insert(0, False)
      print(a_list)

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q5" autocomplete="off" onclick="evaluateMC(name, true)"> [False, 4, 2, True, 8, 6, 5]</li>
         <li><input type="radio" name="Q5" autocomplete="off" onclick="evaluateMC(name, false)"> [4, False, True, 2, 8, 6, 5]</li>
         <li><input type="radio" name="Q5" autocomplete="off" onclick="evaluateMC(name, false)"> [False, 2, True, 6, 5]</li>
      </ol>
      <p id="Q5"></p>

.. Answer = a

.. admonition:: Question

   What is printed by the following program?

   .. sourcecode:: python
      :linenos:

      a_list = [4, 2, 8, 6, 5]
      a_list.pop(2)
      a_list.pop()
      print(a_list)

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q6" autocomplete="off" onclick="evaluateMC(name, false)"> [4, 8, 6]</li>
         <li><input type="radio" name="Q6" autocomplete="off" onclick="evaluateMC(name, false)"> [2, 6, 5]</li>
         <li><input type="radio" name="Q6" autocomplete="off" onclick="evaluateMC(name, true)"> [4, 2, 6]</li>
      </ol>
      <p id="Q6"></p>

.. Answer = c


