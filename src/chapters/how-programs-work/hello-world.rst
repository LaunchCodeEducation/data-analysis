.. _hello-world:

.. _create-replit-account:

Your First Program
==================

We haven’t learned how to code yet, but we can still write and run our first
program. This exercise asks you to create and run small amounts of code, and it
reinforces the LaunchCode principle of learning by doing.

We have used the phrase ``Hello, World`` as an example throughout this chapter
because it represents the traditional first program for a new coder. Printing a
single message is one of the simplest tasks a program can carry out.

``Hello, World`` will be your first program as well. Welcome to the club!

Create a Repl.it Account
------------------------

Throughout this book, you will need to access a code editor to complete
practice problems, exercises, studios, and assignments. If you have not already
done so, create a new account with `Repl.it <https://repl.it/signup>`__. The
site provides a free space to practice coding.

.. figure:: figures/replit-signup.png
   :alt: Repl.it sign-up screen

After you sign in, you will see your *dashboard*, which displays any saved
folders or projects. Since you are just starting out, your dashboard will be
empty.

.. figure:: figures/replit-dashboard.png
   :alt: Repl.it dashboard

Click on *new repl* to begin a new project. Scroll through the options and
select "Python". Next, name your project and click "Create Repl".

.. figure:: figures/replit-newrepl.png
   :alt: Repl.it new repl

The Repl.it Workspace
^^^^^^^^^^^^^^^^^^^^^

Before you dive into your ``Hello, World!`` program, let's take a look at how
to use Repl.it. The workspace consists of three main panels and several menu
functions.

.. figure:: figures/replit-overview.png
   :alt: Repl.it code editor layout

Features to note:

#. **File panel and menus**: On the left, this panel allows you to add extensions, update settings, and
   add, open, or delete files.
#. **Editor panel**: You write your code in this top panel. Click on a file to open it in the
   editor. For most new projects, a ``main.py`` file will be created and opened
   by default.
#. **Console panel**: Any output produced by your code will appear in this
   panel below the editor. The console also displays error messages, test results, and other
   information.
#. **Run button**: Executes any code written in the ``main`` file using the "Run" button at top center.
#. **Collaborate**: Use the "Invite" button at top right to share your projects 
   with other classmates or your TAs for coding collaboration and troubleshooting.

.. admonition:: Note

   The workspace shown above uses the "light" theme (dark text on a white
   background). If you prefer the reverse (light text on a dark background),
   click the gear icon and select the "dark" theme.

Begin Your Coding Journey
-------------------------

Follow this `Hello World link <https://repl.it/@launchcode/HelloWorldPy>`__ to
open a prepared workspace for your first program.

.. admonition:: Note

   .. figure:: figures/replit-fork.png
      :alt: View of a replit created by another user. Includes a 'Fork' button.

   **Fork button**: If you are viewing someone else's project, you can *fork*
   the content (top right) and store a copy of that project to your own account. This
   allows you to edit the files without changing the originals, and it lets
   you use other programmers' work (with permission) to enhance your own.


On line 2 of the editor, type:

   ``print("Hello, World!")``

When you finish typing, click the green "Run" button and observe the output.

.. admonition:: Warning

   Do NOT just copy/paste the code. You will learn best by typing, trying,
   changing, and fixing.

If you typed correctly, you saw the output ``Hello, World!`` If you omitted or
mistyped any characters, then you either saw a misspelled output or an error
message with some tips on what might have gone wrong. Do not worry if you make
mistakes! These experiences still teach you something. Fix any errors and try
again.

Now Play
^^^^^^^^

Once you print ``Hello, World!`` successfully, go back and play around with the
code. Make a change, click "Run", and see what happens. Try to:

#. Change the message that is printed.
#. Figure out what the parentheses do. Will the code work without them?
#. Remove one or both quotation marks. Do we need to include both opening and
   closing quote marks? Is there a difference between using a single or a
   double quote (``'`` vs. ``"``)?
#. Print a number. (Bonus: Print two numbers added together).
#. Print multiple messages one after the other.
#. Print two messages on the same line.
#. Print a message that contains quote marks, such as ``Quoth the Raven
   "Nevermore"``.
#. Other. You choose!

Spend a few minutes trying these changes. Do not worry if you miss some of the
targets. Learning comes through experience, and you WILL learn all the details
behind ``print`` soon.

Once you finish practicing (and hopefully making some mistakes), you will have
a pretty good idea of how the ``print()`` function in Python works.

.. admonition:: Try It

   On paper (or in a document on your computer), write one or two sentences about
   ``print``. You should provide more detail than, “It prints things.”

Check Your Understanding
-------------------------

.. admonition:: Question

   Which of the following correctly prints ``Coding Rocks``? There may be more
   than one valid option.

   a. ``print(Coding Rocks)``
   b. ``print(Coding Rocks);``
   c. ``print('Coding Rocks')``
   d. ``print("Coding Rocks')``
   e. ``print("Coding Rocks")``
