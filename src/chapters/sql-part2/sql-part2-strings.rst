SQL Part 2 - String Functions
=============================

`String Functions <https://docs.microsoft.com/en-us/sql/t-sql/functions/string-functions-transact-sql?view=sql-server-ver15>`__
-------------------------------------------------------------------------------------------------------------------------------

.. list-table::
   :align: left
   :header-rows: 1
   :widths: 15 30 35 20
   
   * - **Function**
     - **Definition**
     - **Syntax**
     - **Value Returned**
   * - `RTRIM <https://docs.microsoft.com/en-us/sql/t-sql/functions/rtrim-transact-sql?view=sql-server-ver15>`__.
     - Removes whitespaces from right of last character.
     - ``SELECT RTRIM('Too many trailing spaces.          ');``
     - Too many extra spaces.
   * - `LTRIM <https://docs.microsoft.com/en-us/sql/t-sql/functions/ltrim-transact-sql?view=sql-server-ver15>`__.
     - Removes whitespaces from left of first character.
     - ``SELECT LTRIM('         Leading spaces');`` 
     - Leading spaces
   * - `LEFT <https://docs.microsoft.com/en-us/sql/t-sql/functions/left-transact-sql?view=sql-server-ver15>`__.
     - Returns length of characters starting at provided character index and moving left.
     - ``SELECT LEFT('hello there!', 7);`` 
     - hello t
   * - `RIGHT <https://docs.microsoft.com/en-us/sql/t-sql/functions/right-transact-sql?view=sql-server-ver15>`__.
     - Returns length of characters starting at provided character index and moving right.
     - ``SELECT RIGHT('hello there!', 3);``
     - re!
   * - `LEN <https://docs.microsoft.com/en-us/sql/t-sql/functions/len-transact-sql?view=sql-server-ver15>`__.
     - Returns the length of a string based on characters, not including trailing spaces.
     - ``SELECT LEN('hello there!'');``
     - 12
   * - `DATALENGTH <https://docs.microsoft.com/en-us/sql/t-sql/functions/datalength-transact-sql?view=sql-server-ver15>`__.
     - Returns the length of a string based on bytes, not including trailing spaces.
     - ``SELECT DATALENGTH('hello there!'');``
     - 12
   * - `CHARINDEX <https://docs.microsoft.com/en-us/sql/t-sql/functions/charindex-transact-sql?view=sql-server-ver15>`__.
     - Can use to find specific character within a string. Returns the index location.
     - ``SELECT CHARINDEX('log', 'catalogue');`` 
     - 5 
   * - `SUBSTRING <https://docs.microsoft.com/en-us/sql/t-sql/functions/substring-transact-sql?view=sql-server-ver15>`__.
     - Returns part of a string. First number is starting index location and second number is ending index location.
     - ``SELECT SUBSTRING('Strings are fun!', 4, 9);``
     - ings are
   * - `REVERSE <https://docs.microsoft.com/en-us/sql/t-sql/functions/reverse-transact-sql?view=sql-server-ver15>`__.
     - Returns the string backwards.
     - ``SELECT REVERSE('Data Analysis');``
     - sisylanA ataD
   * - `UPPER <https://docs.microsoft.com/en-us/sql/t-sql/functions/upper-transact-sql?view=sql-server-ver15>`__.
     - Returns a string either in all upper cases.
     - ``SELECT UPPER('taco');``
     - TACO
   * - `LOWER <https://docs.microsoft.com/en-us/sql/t-sql/functions/lower-transact-sql?view=sql-server-ver15>`__.
     - Returns a string either in all lower cases.
     - ``SELECT LOWER('tACO');``
     - taco
   * - `REPLACE <https://docs.microsoft.com/en-us/sql/t-sql/functions/replace-transact-sql?view=sql-server-ver15>`__.
     - Replaces part of a string using provided patterns.  
     - ``SELECT REPLACE('Beach Streat', 'ea', 'ee');`` 
     - Beech Street
   * - 
     - In this example, the code replaces the 'ea' with 'ee' if the 'ea'  pattern is present. 
     - ``SELECT REPLACE('Read', 'ea', 'ee');``
     - Reed
   * - `CONCAT <https://docs.microsoft.com/en-us/sql/t-sql/functions/concat-transact-sql?view=sql-server-ver15>`__.
     - Combine strings together.
     - ``SELECT CONCAT('Alyce','Cat', 'Frey');``
     - AlyceCatFrey
   * - 
     - Good for working with null values as seen in example 2.
     - ``SELECT CONCAT('Alyce', NULL, 'Frey');``
     - AlyceFrey
   * - `CONCAT_WS <https://docs.microsoft.com/en-us/sql/t-sql/functions/concat-ws-transact-sql?view=sql-server-ver15>`__.
     - Combines strings together with a specified separator value. The separator can be anything you want.
     - ``SELECT CONCAT_WS(' =::= ',  'Alyce', 'Frey');``
     - Alyce=::=Frey
   * - 
     - Works with NULL values like ``CONCAT``.
     - ``SELECT CONCAT_WS('  -  ',  'Alyce', NULL, 'Frey');``
     - Alyce - Frey
   * - `STUFF <https://docs.microsoft.com/en-us/sql/t-sql/functions/stuff-transact-sql?view=sql-server-ver15>`__.
     - Inserts string into another string. The first number indicates where to insert the new chars.
     - ``SELECT STUFF('Pumpkin Pie', 3, 0, 'Add Chars');``
     - PuAdd Charsmpkin Pie
   * - 
     - The second number indicates how many original characters will be deleted upon insertion.
     - ``SELECT STUFF('Pumpkin Pie', 3, 5, 'Delete Chars');``
     - PuDelete Chars Pie




Check Your Understanding
------------------------

.. admonition:: Question
   
   Alyce is working with a dataset that contains information about local businesses.  They  want to create a query that returns titles of local businesses that contain "&".  Which string function should they use?

   a. ``LEN``
   b. ``STUFF``
   c. ``CHARINDEX``
   d. ``RTRIM``

.. admonition:: Question

   Alyce wants to create consistency in the formatting of the state abbreviations of the local business addresses contained in their dataset.  What string function could help with this?
   
   a. ``REVERSE``
   b. ``UPPER``
   c. ``CONCAT``
   d. ``LEFT``

.. admonition:: Question

   Alyce's dataset breaks down the addresses of local businesses into the following columns: ``"Street"``, ``"City"``, ``"State"``, and ``"Zipcode"``.  They would like to create a column that has all items joined to return a complete address in a single column.   Which function would best help with this?

   a. ``CONCAT`` or ``CONCAT_WS`` or ``STUFF``
   b. ``LOWER``
   c. ``REPLACE``
   d. ``LEFT``

.. admonition:: Question

   Alyce is working with a column of phone numbers.  They only need the 7 digit number, not the area code.  However, some of the numbers include the area code, some include the country code and area code, and some only include the seven-digit phone number.  Which function could help them select the 7 digits that she needs?

   a. ``CONCAT_WS``
   b. ``CHARINDEX``
   c. ``RIGHT``
   d. ``RTRIM``