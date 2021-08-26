Exercises: Classes Solutions
============================

.. _oop-part-1:

Step One: Create Your Classes
-----------------------------

Construct three classes that hold the information needed by headquarters as properties. 
One class should be a ``Book`` class and two child classes of the ``Book`` class called ``Manual`` and ``Novel``. 

.. sourcecode:: python

   class Book:
      def __init__(self, title, author, copyright, isbn, pages, times_checked_out, discarded):
         self.title = title
         self.author = author
         self.copyright = copyright
         self.isbn = isbn
         self.pages = pages
         self.times_checked_out = times_checked_out
         self.discarded = discarded

      def checkout(self, uses=1):
        self.times_checked_out = uses + self.times_checked_out

   class Manual(Book):
      def __init__(self, title, author, copyright, isbn, pages, times_checked_out, discarded):
         super().__init__(title, author, copyright, isbn, pages, times_checked_out, discarded)

      def dispose(self, current_year):
        if (current_year - self.copyright) > 5:
            self.discarded = 'Yes'
       
   class Novel(Book):
      def __init__(self, title, author, copyright, isbn, pages, times_checked_out, discarded):
         super().__init__(title, author, copyright, isbn, pages, times_checked_out, discarded)

      def dispose(self):
        if self.times_checked_out > 100:
            self.discarded = 'Yes'


:ref:`Back to Exercises<class-relationships>`

.. _oop-part-2:

Part Two: Create ``Novel`` Object
---------------------------------

Declare an object of the ``Novel`` class for the following tome from the library:

.. sourcecode:: python

  good_read = Novel('Pride and Prejudice', 'Jane Austen', 1813, '1111111111111', 432, 32, 'No')

:ref:`Back to Exercises<class-relationships>`


.. _oop-part-5:

Part Five: Update the Number of Times Checked Out
-------------------------------------------------

.. sourcecode:: python

  good_read.checkout(5)
  good_read.dispose()

  if good_read.discarded == 'No':
    output = "{} has been checked out {} times."
    print(output.format(good_read.title, good_read.times_checked_out))
  else:
    output = "{} has been discarded."
    print(output.format(good_read.title))
 



:ref:`Back to Exercises<class-relationships>`