Comments
=========

As programs get bigger and more complicated, they get more difficult to read.
Good programmers try to make their code understandable to others, but it is
still tricky to look at a large program and figure out what it is doing and
why.

Best practice encourages us to add notes to our programs, which clearly
explain what the program is doing. These notes are called *comments*.

.. index:: ! comment

A **comment** is text within a program intended only for a human reader---it is
completely ignored by the compiler or interpreter. In Python, the ``#``
token starts a comment, and the rest of the line gets ignored. For comments
that stretch over multiple lines, each line must begin with a ``#``.

.. admonition:: Try It

   Experiment by adding and removing comments to the code.

   .. replit:: python
      :slug: CommentExamples01Python
      :linenos:

      # This demo shows off comments!

      # print("This does not print.")

      print("Hello, World!") # Comments do not have to start at the beginning of a line.

      # Here is how
      # to have
      # multi-line
      # comments. 

      print("Comments make your code more readable by others.")

Notice that when you run the program, it still prints the phrase ``Hello,
World``, but none of the comments appear. Also notice the blank lines left in
the code, which are also ignored by the compiler. Comments and blank lines make
your programs much easier for humans to understand. Use them frequently!

.. admonition:: Fun Fact

   There's a few common Engligh terms for the ``#`` token: number symbol,
   pound sign, octothorp, hash, hashtag. What do you call it?
