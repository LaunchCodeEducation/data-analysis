Types of Errors
===============

Each type of error---syntax, runtime, and logic---shows itself in a different
way. Also, some strategies may be more useful for certain types of errors
compared to others.

Stages for Running a Python Program
-----------------------------------

In order to understand programming errors, we should understand that code gets
executed in two stages.

Stage 1 - Parsing
^^^^^^^^^^^^^^^^^

.. index:: ! code parsing

Before code can be run, it must be validated and prepared for execution. This is
known as the **parsing stage**. Think of it like the pre-flight checklist
pilots use before taking off. If errors are found, the plane stays on the
ground.

When we click *Run* to start our code, parsing begins. A lot of detailed tasks
happen behind the scenes during this process, but we just need to know that
parsing checks the syntax and structure of the code. If any mistakes are found,
the program does not launch.

Stage 2 - Execution
^^^^^^^^^^^^^^^^^^^

If parsing finishes without finding any errors, the program is ready to run.
During the **execution stage**, the statements written into our code---printing
to the console, prompting the user for input, making calculations, etc.---get
carried out. Think of this stage as the plane taking flight.

Syntax Errors
-------------

.. index:: syntax

Python can only run a program if the code is *syntactically correct*.
**Syntax** refers to the structure of a language (spoken, programming, or
otherwise) and the rules about that structure. For example, in English,
a sentence must begin with a capital letter and end with some type of
punctuation mark.

.. index::
   single: error; syntax

A **syntax error** occurs when we break one of the rules for a given language.

.. admonition:: Examples

   this sentence contains a syntax error. 

   So does this one

   Here is a Python syntax error:

   .. sourcecode:: Python

      printt("Hello, World!")

For most readers, a few syntax errors are not a big problem. Our brains are
flexible enough to figure out a sentence even if it contains one or more syntax
errors.

Programming languages are not so forgiving. If there is a single syntax error
anywhere in our program, Python will display an error message and immediately
quit. Since syntax is checked during the parsing stage, these errors are
found first.

As you completed the coding exercises in the last several chapters, you
probably spent some time tracking down syntax errors. As you gain experience,
you will make fewer of these mistakes, but they will never disappear completely.
However, you will get good at quickly finding syntax errors.

.. admonition:: Try It!

   Find the syntax errors in the program.

   .. raw:: html

      <iframe height="400px" width="100%" src="https://repl.it/@launchcode/LCHS-Syntax-Error-Example?lite=true" scrolling="no" frameborder="yes" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

   #. What syntax errors did you find?
   #. What was the error message provided by Python in each case?
   #. Pay attention to any line numbers given in the error message.

.. _runtime-error:

Runtime Errors
--------------

.. index::
   single: error; runtime

.. index:: ! exception, ! runtime error

Once the syntax for your code is correct, the program launches. However,
mistakes can still occur and cause the program to crash. These mistakes are
called **runtime errors** because they do not appear until we run the program.
The errors are also called **exceptions** because they usually indicate that
something exceptional (and bad) has happened.

Runtime errors occur during the execution phase of a program, so we only
see them after *all* syntax mistakes are fixed.

Common runtime errors include:

#. Misspelling a variable name.
#. Using an index value that is too large for a given string or list.
#. Incorrect math operations (like dividing by zero).
#. Comparing different data types.

.. admonition:: Examples

   Run the following code to produce an error message. Read the message, fix
   the error, then re-run the program.

   Continue this process until no more error messages appear. Fix only one
   error at a time.

   .. raw:: html

      <iframe height="600px" width="100%" src="https://repl.it/@launchcode/LCHS-Runtime-Error-Examples?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

   Make a note of name (e.g. ``IndexError``) given to each of the runtime
   errors you find in the code. Also notice that the error message gives you
   the line number where the mistake occurred.

The *syntax* in the code is correct, but when the program runs, an error occurs
that Python cannot solve. For example, on line 8, we try to print the value
``first_name``, but the variable does not exist! (In line 4, we defined
``first_Name`` instead).

.. _logic-error:

Logic Errors
------------

.. index::
   single: error; logic
   single: error; semantic

.. index:: ! logic error

The third type of error is the **logic error** (sometimes called a **semantic
error**). If there is a logic error in our code, the program runs successfully
and no error messages appear. However, the program does not work as intended.

The key characteristic of logic errors is that the program we wrote is not the
program we wanted. The code runs just fine, but it does not solve the problem
we need.

Let's take a look at two examples of logic errors:

.. admonition:: Examples

   #. We can use a conditional to tell us if an integer is even or odd:

      .. sourcecode:: python
         :linenos:

         num = 25

         if num%2 == 0:
            print("The number {0} is odd".format(num))
         else:
            print("The number {0} is even".format(num))

      **Console Output**

      ::

         The number 25 is even.

   #. To calculate our daily pay based on our weekly pay, we might try:

      .. admonition:: Example

         .. sourcecode:: python
            :linenos:

            weekly_pay = 600

            daily_pay = weekly_pay / 7
            print(daily_pay)

         **Console Output**

         ::

            85.71428571428571

In the first example, the value ``25`` is odd, but our program calls it even.
The syntax of the code is perfectly correct, and no runtime errors crash the
program, but it gives us the wrong answer. The *logic* of the code is faulty.
Since we know what the answer *should* be for ``25``, we can use that knowledge
to help us correct our code. (There are several ways to fix the error---try to
identify one option).

In the second example, the result surprises us because we thought we were
making at least $100 per day (assuming we work Monday through Friday).
According to the program, though, we only earn about $85 per day. The logic
error occurs because we divided our weekly pay by 7 instead of the 5 days we
actually came in to work.

Identifying logic errors can be tricky because unlike syntax and runtime
problems, running the program produces no error messages that help us identify
the issue. We must examine the output of the program and work backward to
figure out what our code is doing wrong.

Check Your Understanding
------------------------

.. admonition:: Question

   Label each of the following as either a syntax, runtime, or logic error.

   Trying to use a variable that has not been defined.

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> syntax error</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, true)"> runtime error</li>
         <li><input type="radio" name="Q1" autocomplete="off" onclick="evaluateMC(name, false)"> logic error</li>
      </ol>
      <p id="Q1"></p>
   
   Leaving off a close parenthesis, ``)``, when calling ``print``.

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, true)"> syntax error</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> runtime error</li>
         <li><input type="radio" name="Q2" autocomplete="off" onclick="evaluateMC(name, false)"> logic error</li>
      </ol>
      <p id="Q2"></p>
   
   Using the formula ``seconds = minutes * 6`` to calculate the number of
   seconds from a number of minutes.

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, false)"> syntax error</li>
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, false)"> runtime error</li>
         <li><input type="radio" name="Q3" autocomplete="off" onclick="evaluateMC(name, true)"> logic error</li>
      </ol>
      <p id="Q3"></p>

.. Answers = b, a, c

.. admonition:: Question

   Look back at the first logic error example. Which of the following would
   NOT correct the error?

   .. raw:: html

      <ol type="a">
         <li><input type="radio" name="Q4" autocomplete="off" onclick="evaluateMC(name, false)"> In line 3, use <span style="color:#419f6a; font-weight: bold">if num%2 != 0:</span></li>
         <li><input type="radio" name="Q4" autocomplete="off" onclick="evaluateMC(name, false)"> In line 3, use <span style="color:#419f6a; font-weight: bold">if num%2 == 1:</span></li>
         <li><input type="radio" name="Q4" autocomplete="off" onclick="evaluateMC(name, false)"> Switch the odd/even words in the print statements.</li>
         <li><input type="radio" name="Q4" autocomplete="off" onclick="evaluateMC(name, true)"> In line 1, use <span style="color:#419f6a; font-weight: bold">num = 26</span></li>
      </ol>
      <p id="Q4"></p>

.. Answer = d