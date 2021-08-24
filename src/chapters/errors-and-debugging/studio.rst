Studio: Errors and Debugging
============================

The code in this project is broken! Your job is to fix it so we can clear a
rocket for launch.

Requirements:

#. Launch the rocket *only if* the fuel, crew and computer all check out OK.
#. If a check fails, print that information to the console and scrub the
   launch.
#. If all checks be successful, print a countdown to the console followed by
   "Liftoff!"

To get started, you need to clone the starter code from Github. Before you can do this, you need to fork it (as you would on Replit) to make your own personal copy.
Go to the `remote repo <https://github.com/LaunchCodeEducation/errors-and-debugging-studio-data-analysis>`__ and click *Fork* in the upper righthand corner.
In the resulting pop up, select to put the new repository under your personal Github profile.
You can then clone the repository from your profile!

.. admonition:: Note

   If this process is not working for you, that is okay! While we want you to get the hang of forking and cloning remote repos, we also want you to focus on coding!
   Please use the following repls if you need to.

   #. `Syntax Errors <https://replit.com/@launchcode/DebuggingStudio01>`__
   #. `Runtime Errors <https://replit.com/@launchcode/DebuggingStudio02>`__
   #. `Logic Errors <https://replit.com/@launchcode/DebuggingStudio03>`__

Fix Syntax Errors First
-----------------------

Work on this portion of the studio in ``debuggingstudio01.py``.

#. Run the following code as-is and examine the error message. Fix the mistake,
   and then re-run the code to check it.

   ::

      launch_ready = False
      fuel_level = 17000

      if fuel_level >= 20000
         print('Fuel level cleared.')
         launch_ready = True
      else:
         print('WARNING: Insufficient fuel!')
         launch_ready = False

#. The next block of code hides two syntax errors. Run the code as-is to
   find the mistakes.
   
   *Tip*: Only ONE error gets flagged at a time. Fix that ONE problem, and then
   re-run the code to check your work. Avoid trying to fix multiple issues at
   once.

   ::

      launch_ready = False
      crew_status = True
      computer_status = 'green'

      if crew_status and computer_status = 'green':
         print('Crew & computer cleared.')
         launch_ready = True
      else:
         print('WARNING: Crew or computer not ready!')
         launch_ready = False

      if (launch_ready):
         print("10, 9, 8, 7, 6, 5, 4, 3, 2, 1...")
         print("Fed parrot...")
         print("Ignition...")
         print("Liftoff!')
      else:
         print("Launch scrubbed.")

Fix Runtime Errors Next
-----------------------

Work on this portion of the studio in ``debuggingstudio02.py``.

#. Remember to examine the error message for clues about what went wrong. Pay
   close attention to any line numbers given in the message---these will help
   you locate and repair the bug.

   ::

      launch_ready = False
      fuel_level = 27000

      if fuel_Level >= 20000:
         print('Fuel level cleared.')
         launch_ready = True
      else:
         print('WARNING: Insufficient fuel!')
         launch_ready = False

#. Now find and fix the runtime error in a longer code block.

   ::

      launch_ready = False
      fuel_level = 27000

      if fuel_level >= 20000:
         print('Fuel level cleared.')
         launch_ready = True
      else:
         print('WARNING: Insufficient fuel!')
         launch_ready = False

      if launch_ready:
         print("10, 9, 8...")
         print("Fed parrot...")
         print("6, 5, 4...")
         print("Ignition...")
         printt("3, 2, 1...")
         print("Liftoff!")
      else:
         print("Launch scrubbed.")

Solve Logic Errors Last
-----------------------

Logic errors do not generate warning messages or prevent the code from running,
but the program still does not work right. (Refer to the
:ref:`Fixing Logic Errors <fixing-logic-errors>` section if you need to
review).

Work on this portion of the studio in ``debuggingstudio03.py``.

#. First, run this sample code as-is and examine the output. Should the rocket
   have launched? Did it?

   Do not worry about fixing the code yet. You will do that in the next steps.

#. Let's break the code down into smaller chunks. Consider the first ``if/else``
   block below.

   ::

      if fuel_level >= 20000:
         print('Fuel level cleared.')
         launch_ready = True
      else:
         print('WARNING: Insufficient fuel!')
         launch_ready = False

   a. Comment out lines 14 - 25 in the code editor.
   b. Add ``print("launch_ready =", launch_ready)`` after the first block,
      then run the program.
   c. Given the ``fuel_level`` value, should ``launch_ready`` be ``True`` or
      ``False`` after the check? Is the program behaving as expected?

#. Now consider the second ``if/else`` block. Add another
   ``print("launch_ready =", launch_ready)`` after this block and run the
   program.

   ::

      if crew_status and computer_status == 'green':
         print('Crew & computer cleared.')
         launch_ready = True
      else:
         print('WARNING: Crew or computer not ready!')
         launch_ready = False

   Given ``crew_status`` and ``computer_status``, should ``launch_ready`` be
   ``True`` or ``False`` after this check? Is the program behaving as expected?

#. Now consider both ``if/else`` blocks together (keeping the added ``print``
   lines). Run the code and examine the output.

   ::

      launch_ready = False
      fuel_level = 17000
      crew_status = True
      computer_status = 'green'

      if fuel_level >= 20000:
         print('Fuel level cleared.')
         launch_ready = True
      else:
         print('WARNING: Insufficient fuel!')
         launch_ready = False

      print("launch_ready =", launch_ready)

      if crew_status and computer_status == 'green':
         print('Crew & computer cleared.')
         launch_ready = True
      else:
         print('WARNING: Crew or computer not ready!')
         launch_ready = False

      print("launch_ready =", launch_ready)

   Given the values for ``fuel_level``, ``crew_status`` and
   ``computer_status``, should ``launch_ready`` be ``True`` or ``False``? Is
   the program behaving as expected?

#. Ah ha! The value of ``launch_ready`` assigned in the first ``if/else`` block
   got changed in the second ``if/else`` block. This is a common
   mistake---using the same variable to track the results of two separate
   conditionals.
   
   Since the issue is with ``launch_ready``, ONE way to fix the logic error is
   to use a different variable to store the fuel check result. Make your code
   do this, then check if your change works by updating the first ``print``
   statement.

#. Almost done! Modify the final ``if/else`` block to print the countdown and
   ``"Liftoff!"`` if both the fuel check and ``launch_ready`` variables are
   ``True``. Print ``"Launch scrubbed"`` if either check fails.

After you have completed the studio, remember to commit and push your work to the remote repo!
