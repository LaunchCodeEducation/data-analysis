Exercises: Tableau Part 3 
=========================

Getting Started
---------------

1. Download this `Bike Sharing in Washington D.C. Dataset <https://www.kaggle.com/marklvl/bike-sharing-dataset>`__.
   
   A. 2 csv files total. 
  
#. Be sure to read the context and content about this dataset to better understand how and why data was collected.
#. Open the downloaded dataset in Tableau Public.

   A. Create a relationship between the csv files.
   #. ``Dteday`` is a shared column between the two tables.
   
#. Create a new Tableau Public project to answer the below questions.
#. We are going to explore dates and create calculations and parameters with our data that answer our business issue.
#. Your final output will be a dashboard with at least 3 of your charts that provides data useful to the business issue.
#. Here are some `other fun facts about the DC Bike sharing program <https://en.wikipedia.org/wiki/Capital_Bikeshare>`__.

Business Issue: 
^^^^^^^^^^^^^^^

The Bike Sharing program did very well in DC and is still popular today.  Your city is interested in 
creating its own bike sharing program.  You have been tasked to see how the first 2 years went in DC to 
anticipate any factors that might affect usability such as weather, seasons, or holidays.

| A few questions have been provided to help guide your thoughts in this exercise.

EDA
^^^

#. What hours are these bikes most popular with casual riders?  

   #. What about registered riders?

#. What daily trends do you see between casual riders and registered riders from 2011-2012.

   #. Use ``Dteday`` and drill down.

Basic Calculation: 
^^^^^^^^^^^^^^^^^^

#. Do holidays impact casual rentals?  
#. What about registered rentals?

   #. Rename ``Holidays`` from 0 and 1 to “Holiday” and “Non-Holiday” using a calculated field.

#. Does the season increase or decrease usage?  

   #. How does that compare with weather?

#. Use a calculation to rename the ``Seasons`` that is more useful than a number.  

   #. 1 = Spring
   #. 2 = Summer
   #. 3 = Fall
   #. 4 = Winter

#. Use a calculation to rename the ``Weather`` so that it is useful to us humans.

   #. 1 = Clear
   #. 2 = Fog or Mist
   #. 3 = Light precipitation
   #. 4 = Heavy precipitation

#. Does the average temp (°F) impact all riders?
#. Use calculations to convert the ``Temp`` from a “Normalized” scale of 0-1, to °C then finally to °F.

   #. Convert from 0-1 to Celsius using the following formula: **temp = 47 * temp - 8**

      a. `Formula source <https://www.andrew.cmu.edu/user/achoulde/94842/homework/homework5.html>`__.

   #. Next convert to F with the following formula: **(°C * 1.8) + 32**

      a. Quick Check:  The average temp of Jan 1, 2011 is 46.72°F and the average temp of Feb 1, 2011 is 33.86°F.


Table Calculation:
^^^^^^^^^^^^^^^^^^

#. How many total bike rentals occurred in the city between Jan 2011 to Dec 2012?

   #. What are the running totals of bike rides between 2011-2012?

      a. Hint: You can use a quick calculation for this.

Parameter: 
^^^^^^^^^^

#. Duplicate EDA question 1 and create a parameter that will allow a user to choose between hourly casual or registered user usage.

   #. Hint: You are changing a field with a parameter.

Dashboard & Finesse:
^^^^^^^^^^^^^^^^^^^^

#. Make sure your final dashboard has:

   #. Informative titles, axes, and other text elements.

#. Before submitting your work, reflect on these questions. You don't need to submit any answers for these questions.

   #. Would there be any other data that you wish you had as you worked with this data?
   #. Are you happy with your data visualizations?
   #. Is there anything you would like to learn more about for your future projects?

Submitting Your Work
--------------------

When finished make sure to save and publish your work to your Tableau Public account. Copy the URL to your published Tableau project and paste it into the submission box in 
Canvas for **Exercises: Tableau Part 3 - Dashboard Finesse, Calculations and Parameters** and click *Submit*.
