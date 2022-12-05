Tableau Part 3
==============

Reading
-------

This chapter has been broken up into 2 main sections.  Part 1 will cover Dashboard Finesse while Part 2 will cover Tableau concepts involving calculations and parameters.  

Part 1:  Dashboard Finesse
^^^^^^^^^^^^^^^^^^^^^^^^^^

Please watch the following videos (13:42 min total).

To complete this assignment, you are going to continue coding on the viz you worked on in :ref:`Chapter 25<tableau-part1>`, using the World Bank CO2 dataset.

.. list-table:: Tableau Videos with Corresponding Tasks:
      :align: left
      :widths: 20 40 40
      :header-rows: 1

      * - **Video**
        - **Name of Video**
        - **Tasks**
      * - Video 1: 
        - `Combining Sheets On a Dashboard (5:27 min) <https://www.youtube.com/watch?v=yRo5p3MLFMM>`__.
        - Code-a-long using your project from Chapter 25.
      * - Video 2: 
        - `Adding Interactivity to Your Dashboard (4:10) <https://www.youtube.com/watch?v=evP7rzb7Dcs>`__.
        - Code-a-long.
      * - Video 3: 
        - `Dashboard Formatting (4:05) <https://www.youtube.com/watch?v=rbfEdOGbEWQ>`__.
        - Code-a-long. Save and publish your project. 

Part 2: Tableau Calculations & Parameters
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Read the following documentation.

**Basic Calculations:**

`Get Started with Calculations in Tableau <https://help.tableau.com/current/pro/desktop/en-us/calculations_calculatedfields_create.htm>`__.

`Formatting Calculations in Tableau <https://help.tableau.com/current/pro/desktop/en-us/functions_operators.htm>`__.

`Understanding Calculations in Tableau <https://help.tableau.com/current/pro/desktop/en-us/calculations_calculatedfields_understand.htm>`__.

**Table Calculations:**

`Transform Values with Table Calculations <https://help.tableau.com/current/pro/desktop/en-us/calculations_tablecalculations.htm#Create>`__.

`Quick Table Calculations <https://help.tableau.com/current/pro/desktop/en-us/calculations_tablecalculations_quick.htm>`__.

**Parameters:**

`Create Parameters <https://help.tableau.com/current/pro/desktop/en-us/parameters_create.htm>`__.

**Videos:**

| Watch the following videos to help you learn about Tableau calculations functionality and syntax, as well as parameters.   

| The calculation videos are part of a larger calculations playlist.  We suggest you explore more videos in this playlist to learn more about calculations with certain data types and in specific situations.  Keep in mind that we will not be covering LOD (Level of Detail) calculations in this class, so you may skip over those.

.. admonition:: Note 
   
   Each of these learning videos has a workbook that you can download to and code-along with.  You are not required to complete any of these workbooks, but it is suggested that you practice them to become more familiar with Tableau.

.. list-table:: Tableau Videos with Corresponding Tasks:
      :align: left
      :widths: 20 80 
      :header-rows: 1

      * - **Video**
        - **Name of Video**
      * - Video 1: 
        - `Getting Started with Calculations(3:25 min) <https://www.tableau.com/learn/tutorials/on-demand/getting-started-calculations?playlist=269502>`__.
      * - Video 2: 
        - `Calculation Syntax(4:18 min) <https://www.tableau.com/learn/tutorials/on-demand/calculation-syntax?playlist=269502>`__.
      * - Video 3: 
        - `Intro to Table Calculations(3:58 min) <https://www.tableau.com/learn/tutorials/on-demand/intro-table-calculations?playlist=269502>`__.
      * - Video 4: 
        - `Parameters(5:25 min) <https://www.tableau.com/learn/tutorials/on-demand/parameters>`__.
      * - Video 5: 
        - `Using a Parameter to Change Fields(3:58 min) <https://www.tableau.com/learn/tutorials/on-demand/using-parameter-change-fields?playlist=269504>`__.
      

Suggested Resources (not required reading)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Calculations**

`Functions in Tableau <https://help.tableau.com/current/pro/desktop/en-us/functions.htm>`__.

* Good resource for specific functions.
  
`Tips for Working with Calculated Fields in tableau <https://help.tableau.com/current/pro/desktop/en-us/calculations_calculatedfields_tips.htm>`__.

* Keep this as a resource for how to create and edit calculations.

**Table Calculation**

`Table Calculations Types <https://help.tableau.com/current/pro/desktop/en-us/calculations_tablecalculations_definebasic_runningtotal.htm>`__.

* Defines and offers examples for each of the pre-set quick table calculations.

**Parameter Resources**

`Parameter Actions <https://help.tableau.com/current/pro/desktop/en-us/actions_parameters.htm>`__.

* Resource for creating interactive vizzes.

Check Your Understanding
------------------------

.. admonition:: Question

   Match the following calculation types to their definitions.

   .. list-table::
      :align: left
  
      * - Basic calculation
        - Computed values at the data source level as well as the visualization level with additional control over the granularity.
      * - Table Calculations
        - Allows transformation at both the data source and visualization level of detail, without any significant granularity.
      * - Level of Detail (LOD) Calculation
        - Allows transformation at the visualization level only.

.. admonition:: Question

   Which of the following is NOT one of the four basic components of a Tableau calculation?
  
   a. Functions
   #. Level of Detail 
   #. Fields 
   #. Operations 
 
.. admonition:: Question

   When would you use a calculation? (Select all that apply)
   
   a. Segment data
   #. Pivot a table
   #. Convert data type
   #. Aggregate data
   #. Drop a table
   #. No answer text provided. 

.. admonition:: Question

   A parameter can accept values that you specify.  This could include all, a list of possible values, or a range of values.  What determines the availability of these options?

   a. Basic Calculations 
   #. Table Calculations 
   #. Length of Data 
   #. Data Type 

  

.. admonition:: Question

   Match the definitions with their correct terms:

   .. list-table::
      :align: left
      
      * - Table Calculation 
        - Calculations that are part of the query and executed in the data source
      * - Basic or Regular Calculation
        - Local calculations that only occur in your Tableau workbook after any basic calculations have been completed

.. admonition:: Question

   Parameters must be incorporated into something else such as a filter, reference line or calculation field in order to be useful.  
  
   a. True 
   b. False 