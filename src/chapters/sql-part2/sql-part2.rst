SQL Part 2 - String and Date Functions
======================================

Readings
--------

Use the examples and links in the following tables to get familiar with the various SQL functions.

Part 1: `String Functions <https://docs.microsoft.com/en-us/sql/t-sql/functions/string-functions-transact-sql?view=sql-server-ver15>`__.
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
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

Part 2: `Date and Time Data Types and Functions <https://docs.microsoft.com/en-us/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql?view=sql-server-ver15>`__.
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :align: left
   :header-rows: 1
   :widths: 15 30 35 20
   
   * - **Function**
     - **Definition**
     - **Syntax**
     - **Value Returned**
   * - `GETDATE <https://docs.microsoft.com/en-us/sql/t-sql/functions/getdate-transact-sql?view=sql-server-ver15>`__.
     - Returns a timestamp that includes the date and time of the server. 
     - ``SELECT GETDATE()``
     - 2022-01-04 22:12:25.567
   * - `SYSDATETIME <https://docs.microsoft.com/en-us/sql/t-sql/functions/sysdatetime-transact-sql?view=sql-server-ver15>`__.
     - Returns a timestamp that includes the date and time of the server. ``SYSDATETIME`` is more precise with the seconds than ``GETTIME``.
     - ``SELECT SYSDATETIME()``
     - 2022-01-04 22:12:25.5675908
   * - `DATEADD <https://docs.microsoft.com/en-us/sql/t-sql/functions/dateadd-transact-sql?view=sql-server-ver15>`__.
     - Adds a time period to a date. In this example, we are increasing the month value from 02 (February) to 03(March).
     - ``SELECT DATEADD(month, 1, '20220224');``
     - 2022-03-24 00:00:00.000
   * - `DATEDIFF <https://docs.microsoft.com/en-us/sql/t-sql/functions/datediff-transact-sql?view=sql-server-ver15>`__.
     - Calculates and returns the difference of a date part between an end date and a start date.
     - ``SELECT DATEDIFF(day, '2022-11-13', '2022-12-12');``
     - 29
   * - 
     - The first example is comparing the difference between days while the second is comparing months.
     - ``SELECT DATEDIFF(month, '2022-11-13', '2022-12-12');``
     - 1
   * - 
     - The third example is comparing years.
     - ``SELECT DATEDIFF(year, '1984-11-13', '2022-12-12');``
     - 38
   * - `DATENAME <https://docs.microsoft.com/en-us/sql/t-sql/functions/datename-transact-sql?view=sql-server-ver15>`__.
     - Returns a string representing the desired date part.
     - ``SELECT DATENAME(day, '2022-07-25');``
     - 25
   * - 
     - 
     - ``SELECT DATENAME(month, '2022-07-25');``
     - July
   * -
     - 
     - ``SELECT DATENAME(year, '2022-07-25');``
     - 2022
   * - `DATEPART <https://docs.microsoft.com/en-us/sql/t-sql/functions/datepart-transact-sql?view=sql-server-ver15>`__.
     - Returns an integer representing the desired date part.
     - ``SELECT DATEPART(day, '2022-08-21');``
     - 21
   * -
     - 
     - ``SELECT DATEPART(month, '2022-08-21');``
     - 08
   * -
     -  
     - ``SELECT DATEPART(year, '2022-08-21');``
     - 2022
   * - `DAY, MONTH, YEAR <https://docs.microsoft.com/en-us/sql/t-sql/functions/month-transact-sql?view=sql-server-ver15>`__.
     - Each part of a date.
     - ``SELECT DAY('2022-08-21');``
     - 21
   * -
     - 
     - ``SELECT MONTH('2022-08-21');``
     - 8
   * -
     - 
     - ``SELECT YEAR('2022-08-21');``
     - 2022
   * - `CONVERT <https://docs.microsoft.com/en-us/sql/t-sql/functions/cast-and-convert-transact-sql?view=sql-server-ver15#j-using-convert-with-datetime-data-in-different-formats>`__.
     - Paired with GETDATE to `convert other data types into dates and times <https://learn.microsoft.com/en-us/sql/t-sql/data-types/date-transact-sql?view=sql-server-ver15#converting-date-to-other-date-and-time-types>`__ based on the desired format.
     - ``SELECT CONVERT(varchar, GETDATE());``
     - Jan  5 2022  7:25PM
   * - 
     - These examples convert the server date into various formats. The first example is the default format, the second example is format number 7. 
     - ``SELECT CONVERT(varchar, GETDATE(), 7);``
     - Jan 05, 22
   * - `FORMAT <https://docs.microsoft.com/en-us/sql/t-sql/functions/format-transact-sql?view=sql-server-ver15>`__.
     - Used to set the format or reformat dates. This example is using the following date information: Jan  5, 2022  7:38PM. The first example the server date is formatted date, month, year. The time is not requested, so it is not returned.
     - ``SELECT FORMAT(GETDATE(), 'dd/MM/yyyy');``
     - 05/01/2022
   * - 
     - The second example requests only the time in hours and minutes. Note that 'MM' is used for months and 'mm' is used for minutes.
     - ``SELECT FORMAT(GETDATE(), 'hh:mm');``
     - 07:38

Part 3: `More Aggregations and Miscellany <https://docs.microsoft.com/en-us/sql/t-sql/functions/aggregate-functions-transact-sql?view=sql-server-ver15>`__.
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

| The following examples are using the BooksDB.  

.. list-table::
   :align: left
   :header-rows: 1
   :widths: 15 30 35 20
   
   * - **Function**
     - **Definition**
     - **Syntax**
     - **Value Returned**
   * - `SUM <https://docs.microsoft.com/en-us/sql/t-sql/functions/sum-transact-sql?view=sql-server-ver15>`__.
     - Returns sum of all values or DISTINCT values.
     - ``SELECT SUM(ratings_2) FROM BooksDB.dbo.books;``
     - 31108850
   * - `MAX <https://docs.microsoft.com/en-us/sql/t-sql/functions/max-transact-sql?view=sql-server-ver15>`__.
     - Returns the highest value.
     - ``SELECT MAX(ratings_2) FROM BooksDB.dbo.books;``
     - 436802
   * - `MIN <https://docs.microsoft.com/en-us/sql/t-sql/functions/min-transact-sql?view=sql-server-ver15>`__.
     - Returns the lowest value.
     - ``SELECT MIN(ratings_2) FROM BooksDB.dbo.books;``
     - 30
   * - `IS NULL <https://docs.microsoft.com/en-us/sql/t-sql/queries/is-null-transact-sql?view=sql-server-ver15>`__.
     - Determines whether value is null, often used as a condition with ``WHERE``.
     - See examples below.
     - 

.. admonition:: Note

  In example 1, we asked for the TOP 5 rows, but only 3 qualified and were returned.

| **Example 1**

.. sourcecode:: SQL
   :linenos:

    SELECT  TOP 5 title, isbn, original_publication_year
    FROM BooksDB.dbo.books
    WHERE isbn IS NULL AND original_publication_year IS NULL;

| **Value Returned**

| (3 rows affected)

.. list-table::
   :align: left
   :widths: 5 40 15 40

   * -    
     - *title*
     - *isbn*
     - *original_publication_year*
   * - 1
     - BookRags Summary:  A Storm of Swords
     - *NULL*
     - *NULL*
   * - 2
     - A Shade of Blood (A Shade of Vampire, #2)
     - *NULL*
     - *NULL*
   * - 3
     - زغازيغ 
     - *NULL*
     - *NULL*

| **Example 2**

.. sourcecode:: SQL
   :linenos:
   
    SELECT title, original_title
    FROM BooksDB.dbo.books
    WHERE authors LIKE 'Sophocles%' AND original_title IS NULL;

| **Value Returned**

.. list-table::
   :align: left
   :widths: 5 65 30

   * -    
     - *title*
     - *original_title*
   * - 1
     - The Oedipus Cycle: Oedipus Rex/Oedipus at Colonus/Antigone (The Theban Plays, #1-3)NULL
     - *NULL*

.. list-table::
   :align: left
   :widths: 15 30 35 20
   
   * - **Function**
     - **Definition**
     - **Syntax**
     - 
   * - `IS NOT NULL <https://docs.microsoft.com/en-us/sql/t-sql/queries/is-null-transact-sql?view=sql-server-ver15>`__.
     - Determines whether value is not null, often used as a condition with ``WHERE``.
     - See examples below.
     -  

| **Example 1**

.. sourcecode:: SQL
   :linenos:

    SELECT  TOP 5 title, isbn, original_publication_year
    FROM BooksDB.dbo.books
    WHERE isbn IS NOT NULL AND original_publication_year IS NOT NULL;

| **Value Returned**

| (5 rows affected)

.. list-table::
   :align: left
   :widths: 5 55 20 20

   * -    
     - *title*
     - *isbn*
     - *original_publication_year*
   * - 1
     - The Hunger Games (The Hunger Games, #1)
     - 439023483
     - 2008
   * - 2
     - Harry Potter and the Sorcerer's Stone (Harry Potter, #1)
     - 439554934
     - 1997
   * - 3
     - Twilight (Twilight, #1)
     - 316015849
     - 2005
   * - 4
     - To Kill a Mockingbird
     - 61120081
     - 1960
   * - 5
     - The Great Gatsby
     - 743273567
     - 1925

| **Example 2**

.. sourcecode:: SQL
   :linenos:
   
    SELECT title, original_title
    FROM BooksDB.dbo.books
    WHERE authors LIKE 'Sophocles%' AND original_title IS NOT NULL;

| **Value Returned**

.. list-table::
   :align: left
   :widths: 5 50 45

   * -    
     - *title*
     - *original_title*
   * - 1
     - Oedipus Rex  (The Theban Plays, #1)
     - Οἰδίπους Τύραννος
   * - 2
     - Antigone (The Theban Plays, #3)
     - Ἀντιγόνη

.. list-table::
   :align: left
   :widths: 15 30 35 20
   
   * - **Function**
     - **Definition**
     - **Syntax**
     - 
   * - `ISNULL <https://docs.microsoft.com/en-us/sql/t-sql/functions/isnull-transact-sql?view=sql-server-ver15>`__.
     - Replaces a specific null value.
     - See example below.
     - 

.. admonition:: Note

   Note the use of an alias in the example below.
   
.. sourcecode:: SQL
   :linenos:

    SELECT original_title, ISNULL(original_title, title) AS UpdatedOriginalTitle
    FROM BooksDB.dbo.books
    WHERE authors LIKE 'Sophocles%';

| **Value Returned**

.. list-table::
   :align: left
   :widths: 5 30 65

   * -    
     - *original_title*
     - *UpdatedOriginalTitle*
   * - 1
     - Οἰδίπους Τύραννος
     - Οἰδίπους Τύραννος
   * - 2
     - Ἀντιγόνη
     - Ἀντιγόνη
   * - 3
     - NULL
     - The Oedipus Cycle: Oedipus Rex/Oedipus at Colonus/Antigone (The Theban Plays, #1-3)

.. list-table::
   :align: left
   :widths: 15 30 35 20
   
   * - **Function**
     - **Definition**
     - **Syntax**
     - 
   * - `COALESCE <https://docs.microsoft.com/en-us/sql/t-sql/language-elements/coalesce-transact-sql?view=sql-server-ver15>`__.
     - Returns the first value that is not null. Can also be used to test multiple expressions unlike ``ISNULL``. Can be used to address null values when paired with string concatenation.
     - See examples below.
     - 

| **Example 1: Demonstrates returning the first non-null value.**

.. sourcecode:: SQL
   :linenos:
   
    SELECT COALESCE(NULL, 'cat', 'bird');
    SELECT COALESCE('cat', NULL, 'bird');

| **Value Returned**

.. list-table:: 
   :align: left
   
   * - *cat*
   * - *cat*

| **Example 2: Demonstrates using paring ``COALESCE`` with concatenation.**

.. sourcecode:: SQL
   :linenos:

    SELECT COALESCE(original_title, title) + ' by ' + authors AS 'Reading List'
    FROM BooksDB.dbo.books
    WHERE authors LIKE 'Sophocles%';

| **Value Returned**

.. list-table::
   :align: left
   :widths: 5 95

   * -    
     - *Reading List*
   * - 1
     - Οἰδίπους Τύραννος by Sophocles, J.E. Thomas
   * - 2
     - Ἀντιγόνη by Sophocles, J.E. Thomas
   * - 3
     - The Oedipus Cycle: Oedipus Rex/Oedipus at Colonus/Antigone (The Theban Plays, #1–3) by Sophocles, Dudley Fitts, Elena Bono, Robert Fitzgerald

Check Your Understanding
------------------------

.. admonition:: Question
   
   Alyce is working with a dataset that contains information about local businesses.  They  want to create a query that returns titles of local businesses that contain **&**.  Which string function should they use?

   a. **LEN**
   b. **STUFF**
   c. **CHARINDEX**
   d. **RTRIM**

.. admonition:: Question

   Alyce wants to create consistency in the formatting of the state abbreviations of the local business addresses contained in their dataset.  What string function could help with this?
   
   a. **REVERSE**
   b. **UPPER**
   c. **CONCAT**
   d. **LEFT**

.. admonition:: Question

   Alyce's dataset breaks down the addresses of local businesses into the following columns: Street, City, State, and Zipcode.  They would like to create a column that has all items joined to return a complete address in a single column.   Which function would best help with this?

   a. **CONCAT** or **CONCAT_WS** or **STUFF**
   b. **LOWER**
   c. **REPLACE**
   d. **LEFT**

.. admonition:: Question

   Alyce is working with a column of phone numbers.  They only need the 7 digit number, not the area code.  However, some of the numbers include the area code, some include the country code and area code, and some only include the seven-digit phone number.  Which function could help them select the 7 digits that she needs?

   a. **CONCAT_WS**
   b. **CHARINDEX**
   c. **RIGHT**
   d. **RTRIM**

.. admonition:: Question

   Willow has a column in her table containing dates the library branches opened.  She wants to compare them to today’s date. Which function would allow her to do that?

   a. **DATEADD**
   b. **MONTH**
   c. **CONVERT**
   d. **DATEDIFF**
   
.. admonition:: Question

   Willow has a table that contains dates library books are checked out.  She uses the following function in her query: **WHERE DATEPART(MONTH, BorrowDate) = 05**.  What will this return?

   a. Rows of data where books were borrowed in the month of May 
   b. Rows of data where books were borrowed on the 5th day of the month. 
   c. Rows of data where books were borrowed in 2005. 
   d. Rows of data where the same library user borrowed exactly 5 books. 

.. admonition:: Question

   Willow wants to have all the dates in her database in the same format of 'month-day-year'.  She used the following syntax: **FORMAT(ModifiedDate, 'mm/dd/yyyy')** and received an error message.  Why?

.. admonition:: Question

   Francis has a database that contains information about car rentals.  She wants to create a query that would return the oldest car the company owns.  Which aggregation method would be a good fit for this query?

   a. **AVG**
   b. **MIN**
   c. **COUNT**
   d. **MAX**

.. admonition:: Question

   Francis wants to find the car with the highest mileage.  Which aggregation method would be a good option for this query?

   a. **MAX**
   b. **AVG**
   c. **COUNT**
   d. **MIN**

.. admonition:: Question

   Francis wants to create a column that contains a complete address for each car rental office in her database.  She has a column for street address, suite number, city, state, and zip code.  After some quick EDA, she has discovered that every rental office has a street address, city, state, and zip code.  She also discovered that only about 20% have suite numbers while the remaining 80% are null.  What function would let her still join these elements into addresses without worrying about the null elements affecting the final output?  

   a. **COALESCE**
   b. **IS NOT NULL**
   c. **ISNULL**
   d. **IS NULL**