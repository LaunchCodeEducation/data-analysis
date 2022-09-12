Studio: Strings and Lists
==========================

Strings are **ordered collections** of *characters*, which are strings of
length 1. The characters in a string can be accessed using
**bracket notation**.

Lists are ordered collections of items, which can be strings, numbers,
other lists, etc. The items/elements/entries stored in an list can be
accessed using bracket notation.

Strings are **immutable**, whereas lists can be changed.

Strings and lists have **properties** and **methods** that allow us to easily
perform some useful actions.

Part 1: String Modification
----------------------------

Use string methods to convert a word into pseudo-pig latin.

a. Remove the first three characters from a string and add them to the end.
   Ex: ``'LaunchCode'`` becomes ``'nchCodeLau'``. Use a template literal to
   print the original and modified string in a descriptive phrase.
b. Modify your code to accept user input. Query the user to enter the
   number of letters that will be relocated.
c. Add validation to your code to deal with user inputs that are longer than the
   word. In such cases, default to moving 3 characters. Also, the template
   literal should note the error.

`Code it at repl.it <https://replit.com/@launchcode/StringAndListStudio01>`__

Part 2: List and String Conversion
----------------------------------

The ``split`` and ``join`` methods convert back and forth between strings
and lists. Use **delimiters** as reference points to split a string into an
list, then modify the list and convert it back to a printable string.

a. For a given string, use the ``in`` method to check to see if the
   words are separated by commas (``,``), semicolons (``;``) or just spaces.
b. If the string uses commas to separate the words, ``split`` it into an list,
   reverse the entries, and then ``join`` the list into a new comma separated
   string. For example, ``"up,to,code,fun"`` becomes ``"fun,code,to,up"``.
c. If the string uses semicolons to separate the words, ``split`` it into an
   list, alphabetize the entries, and then ``join`` the list into a new
   hyphen separated string. For example, ``"up;to;code;fun"`` becomes
   ``"code-fun-to-up"``.
d. If the string uses spaces to separate the words, ``split`` it into an list,
   reverse alphabetize the entries, and then ``join`` the list into a new
   space separated string. For example, ``"to code up fun"`` becomes
   ``"up to fun code"``.
e. *Consider*: What if the string uses 'comma spaces' (, ) to separate the
   list? Modify your code to produce the same result as part "b", making sure
   that the extra spaces are NOT part of the final string.

`Code it at repl.it <https://replit.com/@launchcode/StringAndListStudio02>`__

Part 3: Optional Fun With Multi-dimensional Lists 
-------------------------------------------------

Lists can store other lists!

a. The cargo hold in our shuttle contains several smaller storage spaces. Use
   ``split`` to convert the following strings into four cabinet lists.
   Alphabetize the contents of each cabinet.

   i. ``"water bottles, meal packs, snacks, chocolate"``
   ii. ``"space suits, jet packs, tool belts, thermal detonators"``
   iii. ``"parrots, cats, moose, alien eggs"``
   iv. ``"blankets, pillows, eyepatches, alarm clocks"``

b. Initialize a ``cargoHold`` list and add the cabinet lists to it. Print
   ``cargoHold`` to verify its structure.
c. Query the user to select a cabinet (0-3) in the ``cargoHold``.
d. Use bracket notation and a template literal to display the contents of
   the selected cabinet. If the user entered an invalid number, print an
   error message instead.
e. *Bonus to the Bonus*: Modify the code to query the user for BOTH a cabinet in
   ``cargoHold`` AND a particular item. Use the ``includes`` method to check
   if the cabinet contains the selected item, then print ``"Cabinet ____
   DOES/DOES NOT contain ____."``

`Code it at repl.it <https://replit.com/@launchcode/StringAndListStudio03>`__
   

Submitting Your Work
---------------------

You should have **2** repls when finished with the studio. Copy the URLs to your repls, separating each URL with a semi-colon and paste them into the submission box in Canvas for **Studio: Strings and Lists** and click *Submit*.

If you did Part 3, submit that through Canvas as well.

