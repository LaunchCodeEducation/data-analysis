Exercises: Tableau Part 1 - Introduction to Visualization 
=========================================================

Getting Started
---------------

Work through `World Happiness Dashboard <https://towardsdatascience.com/world-happiness-dashboard-in-tableau-4dc504212288>`__ in Tableau to create your own dashboard. This walkthrough uses the `World Happiness Dataset <https://www.kaggle.com/unsdsn/world-happiness?select=2019.csv>`__ on Kaggle.

| Don't hesitate to change colors or add details to your visualizations.

| `Link to the dataset <https://www.kaggle.com/unsdsn/world-happiness?select=2019.csv>`__, if the hyperlink in the article is not working.

Step-by-step Guide for this Walkthrough
-----------------------------------------

   As you read through the article, don't hesitate to try out what the videos demonstrate or just experiment with Tableau to figure things out. We have outlined the steps from the article below so you don't lose your place!


#. Download the ``2019.csv`` file from the Kaggle dataset.
#. **Viz 1: Happiness Score of Countries — 2019**

   A. Create the Map

      #. Drop the **Latitude** pill into the *Rows* shelf
      #. Drop **Longitude** pill into *Columns* shelf
      
   #. Drop **Country or region** onto the *Marks Card*. 

      #. This is added as a *Detail*. Look at the icons to verify.
      
   #. Select **Score** and drag it onto the *Color* box contained in the *Marks* card.
   #. Rename your sheet: either double click on “Sheet 1” in the View or right click on the Sheet tab to update the name.

      #. If only updating the view, the sheet tab name will not change. 

#. **Viz 2: Happiness Score vs GDP and Healthy Life Expectancy**

   A. Drag **Score** onto the *Row* shelf

      #. It will automatically aggregate as a SUM of Score.
      #. To remove that, find the drop down menu on the right side of the pill and select “Dimension”.

   #. Drag **GDP per capita** onto the *Columns* shelf

      #. Convert this into a “Dimension”, too.
      
   #. Drag the **Healthy Life Expectancy** into the *Color* box found in the *Marks* card.
   #. Rename your sheet.

#. **Viz 3: Freedom and Social Support vs Score**

   A. Drop **Score** into the *Columns* shelf

      #. Within the **Score** pill, find the drop down menu and select “Dimension”
      
   #. Drag the **Freedom to make life choices** pill onto the *Rows* shelf.

      #. Notice that it changed to a SUM - keep it this way

   #. Drag the **Social Support** pill onto the *Row* shelf

      #. Notice that is also now a SUM - keep it this way
      
   #. To rename an axis, double-click on it and make the changes desired.
   #. Rename your sheet

#. **Make a Dashboard**

   A. Use the tab to create a new dashboard
   #. Drag your sheets onto the dashboard.
   
   .. admonition:: Note
         
      If you only renamed the sheets within your view, the tabs will not have changed.  This is okay.  You can either update the tab names now or work with Sheet 1, Sheet 2, and Sheet 3.  

   #. You may make it identical to the dashboard in the article, or design it yourself.

 
Submitting Your Work
--------------------

When finished make sure to save and publish your work to your Tableau Public account. Copy the URL to your published Tableau project and paste it into the submission box in 
Canvas for **Exercises: Tableau Part 1 - Introduction to Visualization** and click *Submit*.

