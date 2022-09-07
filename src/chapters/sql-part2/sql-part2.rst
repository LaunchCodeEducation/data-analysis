SQL Part 2 - String and Date Functions
======================================

Readings
--------


Check Your Understanding
------------------------

.. admonition:: Question

   Alyce is working with a dataset that contains information about local businesses.  They  want to create a query that returns titles of local businesses that contain **&**.  Which string function should they use?

  a. LEN
  b. STUFF
  c. CHARINDEX
  d. RTRIM

.. admonition:: Question

   Alyce wants to create consistency in the formatting of the state abbreviations of the local business addresses contained in their dataset.  What string function could help with this?
   
   a. REVERSE
   b. UPPER
   c. CONCAT
   d. LEFT

.. admonition:: Question

   Alyce's dataset breaks down the addresses of local businesses into the following columns: Street, City, State, and Zipcode.  They would like to create a column that has all items joined to return a complete address in a single column.   Which function would best help with this?

   a. CONCAT or CONCAT_WS or STUFF
   b. LOWER
   c. REPLACE
   d. LEFT

.. admonition:: Question

   Alyce is working with a column of phone numbers.  They only need the 7 digit number, not the area code.  However, some of the numbers include the area code, some include the country code and area code, and some only include the seven-digit phone number.  Which function could help them select the 7 digits that she needs?

   a. RIGHT
   b. RTRIM
   c. CONCAT_WS
   d. CHARINDEX

.. admonition:: Question

   Willow has a column in her table containing dates the library branches opened.  She wants to compare them to today’s date. Which function would allow her to do that?

   a. DATEDIFF
   b. MONTH
   c. CONVERT
   d. DATEADD
   
.. admonition:: Question

   Willow has a table that contains dates library books are checked out.  She uses the following function in her query: **WHERE DATEPART(MONTH, BorrowDate) = 05**.  What will this return?

   a. Rows of data where books were borrowed in the month of May 
   b. Rows of data where books were borrowed on the 5th day of the month. 
   c. Rows of data where books were borrowed in 2005. 
   d. Rows of data where the same library user borrowed exactly 5 books. 

.. admonition:: Question

   Willow wants to have all the dates in her database in the same format of ‘month-day-year’.  She used the following syntax: **FORMAT(ModifiedDate, ‘mm/dd/yyyy’)** and received an error message.  Why?

.. admonition:: Question

   Francis has a database that contains information about car rentals.  She wants to create a query that would return the oldest car the company owns.  Which aggregation method would be a good fit for this query?

   a. MIN
   b. AVG
   c. COUNT
   d. MAX

.. admonition:: Question

   Francis wants to find the car with the highest mileage.  Which aggregation method would be a good option for this query?

   a. MAX
   b. AVG
   c. COUNT
   d. MIN

.. admonition:: Question

   Francis wants to create a column that contains a complete address for each car rental office in her database.  She has a column for street address, suite number, city, state, and zip code.  After some quick EDA, she has discovered that every rental office has a street address, city, state, and zip code.  She also discovered that only about 20% have suite numbers while the remaining 80% are null.  What function would let her still join these elements into addresses without worrying about the null elements affecting the final output?  

   a. COALESCE
   b. IS NOT NULL
   c. ISNULL
   d. IS NULL