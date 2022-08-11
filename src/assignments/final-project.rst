.. _finalProject:

Assignment #4: Final Project
============================

Overview of the Final Project
-----------------------------

The final project is an opportunity to showcase your analysis skills from EDA to 
visualization and produce a project for your professional portfolio. The project 
is broken into five checkpoints.

#. :ref:`Selecting your business issue and dataset<checkpoint1>`
#. :ref:`EDA<checkpoint2>`
#. :ref:`Cleaning data<checkpoint3>`
#. :ref:`Manipulate, interpret, and visualize data<checkpoint4>`
#. :ref:`Modelling data<checkpoint5>`

Examples of final projects to help you understand the requirements and complete your own.

.. _checkpoint1:

Checkpoint 1: Choose your Data
------------------------------


For this assignment, you must search for a dataset you want to get to know very well. So 
far in this class, your data has been assigned to you. Here, you have the opportunity to 
discover all of the free and readily available data out in the world for public consumption. 

You have creative liberty with two decisions here. One is the data you wanted to use, the 
other is the business issue you want to ask. Perhaps you have a burning question about 
climate change, local home prices, or average daily screen usage. The scale of your 
question can be as macro or as micro as you wish. 

For inspiration, think about what brought you to this class in the first place. Is it to 
get a new job? Maybe you’ll look for more Bureau of Labor datasets or ask a different 
question of the Assignment 3 (9 to 5) data. Maybe you’ll want to dive into some data for 
a field you’re interested in joining. Healthcare, finance, advertising, manufacturing, 
logistics, mapping, are just a few fields with growing need for analysts. You could also 
just have a hobby that you want to learn more about, such as knitting or running. Choose 
what fuels your interest. This can be an expansion or alternative analysis of a dataset 
we’ve used in class so far.

For some, your inspiration may come instead from doing a little data surfing. We’ve found most 
of the exercise and studio datasets from `Kaggle <https://www.kaggle.com/datasets>`__. 
`Tableau <https://public.tableau.com/en-us/s/resources?qt-overview_resources=1#qt-overview_resources>`__ 
lists some solid choices as well. You are not limited to just these resources for sourcing 
your data. If you are interested in looking at regional data, there are resources like the 
`STL Regional Data Exchange <https://rdx.stldata.org/search/type/dataset>`__, 
`OpenDataPhilly <https://www.opendataphilly.org/organization/city-of-philadelphia>`__, and 
`OpenDataKC <https://data.kcmo.org/>`__ to check out.

Here's what you should consider when sourcing your data:

* Is it in a format you know how to work with? 
* Is it licensed for your educational use?
* Does it require a request process and will that prevent you from turning in your checkpoints on time?
* If you do find a cool set of data that requires a lengthy request process, talk to your mentors. They may know about alternatives you can use.



Kaggle Tips
~~~~~~~~~~~

**Usability**

Kaggle shows a usability score for datasets. Keep this figure in mind when searching for data. 
Usability score takes into account such factors as how dirty the data is, how much context is 
given, and what information is present in the columns. Hover over a usability score to see the 
criteria. Do not select a dataset with a usability score under 7.

**Size**

Keep in mind that larger datasets will not load in Tableau. Check the size of the dataset you 
are interested in and make sure it is well below 50 MB.  If you are struggling with finding a 
dataset that fits the size limit, check the sizes of the files within the dataset to see if 
you could use one or two CSVs instead of the whole thing.

**Licensing**

You can find the licensing information for each dataset on the main dataset page. Click on 
the license type to read more about what you can and can not do with the dataset. Some 
authors may choose a license type that requires you to credit the source of the dataset on 
your work. The license type you should be looking for is CC0: Public Domain. This means that 
the dataset is not copyrighted and you may do with it what you will. However, you may not in 
any way imply that your work is endorsed by the author. For example, if your dataset is put 
together by the Bureau of Labor Statistics, you may not claim that the Bureau of Labor 
Statistics believes your work to be the most accurate representation of the workforce. 

**Tags**

If you are interested in a specific topic or type of analysis (i.e. regression), you can 
search for tags. This can help narrow down the options. For example, if you want to search 
for some data about education and the UN, you might use “United Nations” as a search term 
and specify that datasets should be tagged with the “education” tag. 

**Additional Notes**

Keep an eye out for non-Latin characters, such as Russian. During the visualization lesson, 
you may remember the Goodreads dataset had some errors that you were able to work around. 
Those errors were due to the Pandas not being able to process non-Latin characters properly. 
If you encounter this, you may have to clean out those rows causing trouble, leading to 
inaccuracies in your analysis. 

Submitting Your Work
~~~~~~~~~~~~~~~~~~~~
Before you submit your work, download the dataset to ensure that it will meet your needs. 
If your computer cannot download the dataset due to its size, try a similar dataset that 
is smaller or download the individual files. Open up the file(s) using the default 
application for your computer to see that there are in fact numbers in there and to see 
how many rows are in the file so that you don’t run into an issue with Tableau later. 
Tableau Public works best when the dataset is below 10 million rows.

When you are confident in your choice, create a new document on your computer using your 
word-processing program. Put your name in the right-hand corner and type up your business 
issue and provide the link to your chosen dataset. Submit your document on the Canvas 
submission page for Graded Assignment #4: Checkpoint 1.

.. _checkpoint2:

:ref:`Back to Final Project Overview<finalProject>`

Checkpoint 2: EDA
-----------------

Before You Start
~~~~~~~~~~~~~~~~

If you have not received any feedback from Checkpoint 1, check in with your mentors before 
working on Checkpoint 2. 

Getting Started
~~~~~~~~~~~~~~~

Fork `this GitHub repository <https://github.com/gildedgardenia/eda-checkpoint>`__ and and 
clone it to your computer. If you need a refresher on how to do this see 
:ref:`Instruction for Using Github w/Jupyter Notebooks<usingGitHubNotebooks>`.  Follow the instructions 
within the notebook using your chosen dataset. Add notes about your EDA where directed to. 

Submitting Your Work
~~~~~~~~~~~~~~~~~~~~

When finished with your EDA make sure to push your changes up to Github. Copy the link to your Github 
repository and paste it into the submission box in Canvas for Graded Assignment #4: Checkpoint 2 
and click submit.

.. _checkpoint3:

:ref:`Back to Final Project Overview<finalProject>`

Checkpoint 3: Cleaning Data
---------------------------


Before You Start
~~~~~~~~~~~~~~~~

You may find it easier to work on Checkpoint Three and Checkpoint Two in tandem. We encourage you to do 
whatever is easiest for you, but you should be making sure that you keep the appropriate work in each 
notebook. If you put a cleaning step in your EDA notebook, you may not receive a full grade for this 
checkpoint. If you want to change anything about what you have done so far in earlier checkpoints, you do 
not have to re-submit any previous checkpoints unless your mentor requests you do so.

Getting Started
~~~~~~~~~~~~~~~

Fork `this GitHub repository <https://github.com/gildedgardenia/cleaning-data-checkpoint>`__ and and 
clone it to your computer. Follow the instructions within the notebook using your chosen dataset. 
Add notes about your process where directed to. 

After you have cleaned your data, you will want to export your clean dataset from your notebook. 
The following `article <https://medium.com/@kasiarachuta/importing-and-exporting-csv-files-in-python-7fa6e4d9f408>`__ 
will provide you with the syntax for this step. The rest of the checkpoints should be completed 
using your cleaned data.

Submitting Your Work
~~~~~~~~~~~~~~~~~~~~

When finished cleaning your data, make sure to push your changes up to Github including your 
new cleaned dataset. Copy the link to your Github repository and paste it into the submission box 
in Canvas for Graded Assignment #4: Checkpoint 3 and click submit.

.. _checkpoint4:

:ref:`Back to Final Project Overview<finalProject>`

Checkpoint 4: Tableau Story
---------------------------

Before You Start
~~~~~~~~~~~~~~~~

You want to first check to see if you have received any feedback from Checkpoints 2 and 3. This 
feedback could influence the direction of your work on Checkpoint 4. If you want to change anything 
about what you have done so far in earlier checkpoints, you do not have to re-submit any previous 
checkpoints unless your mentor requests you do so. You can simply add any updated work and notes to 
the current checkpoint.

Getting Started
~~~~~~~~~~~~~~~

For this checkpoint, you will need to manipulate your data and produce a Tableau story that shows off 
skills from class, such as filtering and table calculations. You may find yourself wanting to use 
Pandas and Jupyter notebooks for data manipulation. If you do, make sure to add code comments 
explaining your thought process and push your work up to Github. No matter what visualizations you 
add to your Tableau story, all of your captions should include explanations as to your thought 
process for each visualization. The first caption should include a link to your dataset and the 
final story point should include links to any supporting materials, such as the Github repository 
if you used a Jupyter notebook for this checkpoint. 

Submitting Your Work
~~~~~~~~~~~~~~~~~~~~

When finished paste the link to your Tableau story into the submission box in Canvas for Graded 
Assignment #4: Checkpoint 4 and click submit.

.. _checkpoint5:

:ref:`Back to Final Project Overview<finalProject>`

Checkpoint 5: Modeling Data 
---------------------------

Before You Start
~~~~~~~~~~~~~~~~

While working on this checkpoint, you will also have to present your work on the previous four 
checkpoints. We included notes on final project presentations at the end of this assignment. 
If you want to change anything about what you have done so far in earlier checkpoints, you do not 
have to re-submit any previous checkpoints unless your mentor requests you do so.

Getting Started
~~~~~~~~~~~~~~~

Fork `this GitHub repository <https://github.com/gildedgardenia/checkpoint-five>`__ and clone it to your 
computer. Follow the instructions within the notebook to create a linear regression model with your cleaned 
dataset. If it doesn't work out very well, that is alright. The most important thing is that you train a 
model and summarize the results.

Submitting Your Work
~~~~~~~~~~~~~~~~~~~~

When finished with your linear regression model, make sure to push your changes up to Github. Copy the link to 
your Github repository and paste it into the submission box in Canvas for Graded Assignment #4: Checkpoint 
5 and click submit.

Final Project Presentations
---------------------------
Over the course of the final two days of class, you and your classmates will present your work on your 
final project. Your mentors will let you know how much time you have for each presentation. Remember to 
practice your presentation in advance so you can make sure that you are within the time limit and leave 
room at the end for questions from your classmates. 

Your presentation should cover:
 
#. Your business issue and how you chose your dataset.
#. Anything of note you learned in the EDA process.
#. Anything of note you learned in the cleaning process.
#. Your Tableau story.
 

In addition to presenting your Tableau story from Checkpoint Four, you are welcome to make additional 
slides talking about the first three points if you find that helpful. You are not required to do so, 
however, and can use your Tableau story as your sole presentation aid if you prefer.

:ref:`Back to Final Project Overview<finalProject>`