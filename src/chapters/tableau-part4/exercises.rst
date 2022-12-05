Exercises: Tableau Part 4 - Stories and Dates
=============================================

Getting Started
---------------

Create Your Own Interactive Resume
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

| Now that you are almost done with CoderGirl, let’s create an interactive resume that will show off your skills using Tableau.  Since this resume will be all about you, you are going to be creating and editing the data.   You can choose to create a dashboard for your resume or a story.   Since we are using Tableau Public for this resume, you should not share any contact information for this project.  

.. admonition:: Note
   
   If you do not feel comfortable creating a resume about yourself, you may choose to create an interactive resume about a fictional character or historical figure of your choice. 

| Your interactive resume should contain:

1. At least one gantt chart that displays a relevant timeline for your resume.  
#. And at least one other type of visualization that is relevant to your resume.

.. _part1-how-to:

Part 1: How to Create a Resume In Tableau Public
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. `How to Create an Interactive Resume in Tableau <https://www.tableau.com/blog/how-create-interactive-resume-tableau>`__.

   #. Don't feel limited with your visualizations here.  
   #. Browse the `Interactive Resume Gallery <https://www.tableau.com/interactive-resume-gallery>`__, for inspiration.
   
      A. You can download a viz that you like and explore how they created their resume.

#. Optional resources to help you build your Interactive Resume:

   #. `5 Tips on Creating an Interactive Resume using Tableau <https://www.tableau.com/blog/5-tips-creating-visual-resume-using-tableau-40558>`__.
   #. `How to make an interactive resume in Tableau (50 min) <https://www.tableau.com/learn/webinars/how-make-interactive-resume-tableau?ssologin=true#video>`__.

      A. This video will teach you how to make a gantt chart and a lollipop chart. 
   
   #. `Create Your Interactive Resume in Tableau Public? Video (48 min) <https://www.youtube.com/watch?v=YlyO_InVI-E>`__.

      A. This video will teach you how to create an obsolescence chart, as well as how to customize a lollipop cart, and add links to your dashboard.

Part 2: Creating the Data
^^^^^^^^^^^^^^^^^^^^^^^^^

| You are creating the data for this project, as it is your resume.  In order to do this, you will need to use a spreadsheet program that will allow you to save and download csv files.  This could be Excel, Google Sheets, or Numbers.  Tableau likes columnar formats, meaning you organize your data by columns.  For example, you make a spreadsheet about volunteer work that has a column for the name of the organization/activity, the start date and end date, and a description.  

| Once your data has been entered, you will need to save and download your file.  Make sure you download it as a csv file.  We suggest creating a folder for your spreadsheets and remembering its location as you might be adding to it as you work on this exercise.

**A few notes on your data:**

| *Dates:*

#. Start and End Time: 

   #. If you don't remember exactly when you started or ended an experience, use your best judgement and be consistent.  
   #. Also when you are adding dates into your spreadsheet, look in the data entry line to verify the formatting as well as the cell you are entering data into.  

   .. figure:: figures/check-your-dates.png
      :alt: A discrepancy between the Google Sheet cell and the Google Sheet function row. 

   In this example, notice that cell C2 says “Jun-02” which the creator of the data set meant to be “June 2002”, but the entry line is formatting it as “6/2/2021”.  By manually entering the date into the entry line, the correct format “6/1/2002” was entered and then uploaded to Tableau.  Things to double check before you upload.

#. Formats:  When you open a file in Tableau, you might notice that Tableau thinks your dates are numbers or strings.  

   #. You can convert these to dates in the preview page by selecting the column you want to change, clicking on the dropdown menu and selecting “Change Data Type” then pick what data type you want the value to be.  

   .. figure:: figures/string-date-change.png
      :alt: Data preview page in Tableau Public showing how to change data type. 

   In this example, “Start Date” is a string not a date.  Using the Dropdown menu, we were able to change data type from string to date. 

#. Remembering Things Once Working In Tableau:

   #. Once you start working in Tableau with your data, you might want to change your data. 
   #. There could be things you want to add, redesign, or you might have caught a typo.  
   #. You can modify your data.  Go back to your spreadsheet and make your changes.  

      A. For example, you decided that you want to add location to one of your spreadsheets.  Add the column (or columns) to your spreadsheet.  Depending on the program you use, in Excel you might need to only save it to update all your changes, or if using Google Sheets  you will need to download it again as a csv and then replace the old version with the new one.  Once that is done, you can refresh your data in Tableau.

   .. figure:: figures/refresh-your-data.png
      :alt: Image showing how to use the Data menu to refresh your data

   The data menu allows you to refresh your data.   After refreshing, a notice window will appear informing you that “If you have modified filters or hidden fields you may be replacing important data.  Are you sure you wish to proceed?” Select “Yes”. Make sure that you review your worksheet to make sure it functions correctly.

Part 3:  Create your Charts
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Now that you have your data, use it to create your Gantt chart and a second chart of your choice.  
Refer to the resources in :ref:`Part 1<part1-how-to>` for guidance.

Submitting Your Work
--------------------

When finished make sure to save and publish your work to your Tableau Public account. Copy the URL to your published Tableau project and paste it into the submission box in 
Canvas for **Exercises: Tableau Part 4 - Stories and Dates** and click *Submit*.
