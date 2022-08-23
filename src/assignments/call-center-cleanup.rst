.. _callCenterCleanup:

Assignment #2: Call Center Cleanup
==================================

For this assignment, we will be working with call center data. You can start 
working on the assignment after the first lesson on Exploratory Data Analysis. 
Make sure to read the whole assignment before starting anything! As you code 
along in the Jupyter notebook, you are asked to make note of the results of 
your analysis. Do so by clicking on the results box and adding your notes 
beside each question.

Business Issue and Understanding
--------------------------------

You are working for a company that has two call centers: the North Call 
Center and the South Call Center. The company is looking to possibly hire five 
additional reps to enhance customer experience. Your task is to explore how 
efficient the current reps are in each branch to determine which branch would 
benefit from additional assistance.

How the Call Center Works
~~~~~~~~~~~~~~~~~~~~~~~~~

Call center representatives are assigned queues. When calls are assigned to a 
queue, the call is assigned to the next person in line in the queue. After a call 
is assigned to a representative, the amount of time between assignment and the 
call starting is divided into busy minutes and not ready minutes. If the call is 
incoming and a customer is waiting on the phone for a rep, the time is split into 
three categories: busy minutes, not ready minutes, and incoming call wait time. 
Once the rep has the customer on the phone, there might be during call wait time, 
where the call is put on hold while the rep gets an answer for the customer.

Notes about the Dataset
~~~~~~~~~~~~~~~~~~~~~~~

If you haven't worked in a call center before, these notes might help you 
throughout your analysis.

* The call purpose is tagged for each call.
* The time of the call is tagged in 1 hour blocks starting at 9:00 AM and ending 
  at 5:00 PM.
* Calls are tagged as incoming or outgoing.
* Reps are assigned to queues. When the reps are working, they take calls in the 
  order of their queue.
* A call that is dropped due to technical error or missed by the center because they 
  have reached maximum capacity is a lost call.
* An abandoned call is when the customer hangs up because they have been waiting for 
  too long.
* Busy Minutes: the amount of time after a call comes in or needs to go out where the 
  assigned rep is not available because they are busy with other customers.
* Not Ready Minutes: the amount of time after a call comes in or needs to go out where 
  the assigned rep is not available because they are not ready (for example, getting 
  water).
* Incoming Wait Time - amount of time after assigned rep is available to take the call 
  customer waits for representative to pick up a call. This is tracked in seconds.
* During Call Wait Time - amount of time during call that customer has to wait for 
  representative

Getting Started
---------------

Fork `this GitHub repository <https://github.com/gildedgardenia/call-center-cleanup-assignment>`__
and clone it to your computer. If you need a refresher on how to do this see 
:ref:`Instruction for Using GitHub w/Jupyter Notebooks<usingGitHubNotebooks>`. Follow the 
instructions in the Call Center Cleanup.ipynb notebook to complete the assignment. 

Submitting Your Work
--------------------

When you are finished, make sure to push your changes up to GitHub. Copy the link to your GitHub 
repository and paste it into the submission box in Canvas for Graded Assignment #2: Call Center Cleanup and click *Submit*.