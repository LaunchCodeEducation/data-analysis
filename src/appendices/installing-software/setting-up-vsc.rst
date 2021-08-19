.. _vsc-install:

Setting Up Visual Studio Code
=============================

.. index:: ! IDE, ! integrated development environment

Before we start coding on our computer, we need to make sure we have the right tools! Programmers use **integrated development environments** (IDE) to write and run their code.
The development environment we will be using for this class is Visual Studio Code.
In addition to simply writing and running code, Visual Studio Code has tools that recognize errors in our code and has an integrated terminal so we can navigate through our filesystem to find the files that need our attention.

.. note::

   Visual Studio Code is very customizable. Once you have everything set up, you can take additional steps to personalize your workspace such as changing the theme.

Go to the Visual Studio Code `download page <https://code.visualstudio.com/download/>`_ and download the appropriate version for your operating system.

Open your new copy of Visual Studio Code. To open one of your coding projects, go to `File > Open` and select the project you want to work on.

To start working with the terminal, go to `Terminal > New Terminal`. The new terminal window will open on the bottom right.

Windows Users
-------------

The terminal is in powershell, not Git Bash. To change this, open the Command Palette by going to `View > Command Palette`. Type "Select Default Shell" in the search window and select "Select Default Shell" from the menu.
Change the default to Git Bash.

Now every time you open the terminal, it will default to bash!

.. _vsc-python-extension:

Extensions and Themes
---------------------

One of the great things about Visual Studio Code is that it is highly-customizable.
You can add extensions to work with specific languages or change the color theme to one that suits you better!

Required Extensions
^^^^^^^^^^^^^^^^^^^

For this class, you will need to add the following extensions to Visual Studio Code:

#. `Python <https://marketplace.visualstudio.com/items?itemName=ms-python.python>`__

   .. admonition:: Note

      In order for this extension to work properly, you need to have followed the steps to :ref:`install Python <python-system-install>` on your machine.

#. `Github Pull Requests and Issues <https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github>`__

   .. admonition:: Note

      This extension requires you to authorize access to your Github account.
      Use your Personal Access Token in place of your password.

Optional Extensions
^^^^^^^^^^^^^^^^^^^

As you code more, you may find new tools and extensions you want to add to Visual Studio Code. It is your local development environment, so configure away!
Even a simple change like switching up the themes to different colors to make your coding life easier!

.. _running-vsc:

Testing Your Installation
-------------------------

Once you have installed Visual Studio Code and the required extensions for this class, it is time to test it out with a simple Python program. 

.. admonition:: Warning

   If you have not installed the :ref:`required Python extension <vsc-python-extension>`, this next section will not work!

#. Open up the folder where you want to keep your work for this class and create a new folder inside called "Testing VSC"
#. Open up your ``Testing VSC`` folder in Visual Studio Code.
#. Create a new file in your ``Testing VSC`` folder called ``main.py``. To create a new file, you can either select *File > New File* or when hovering over the project name in the Explorer pane, you will see four icons pop up. The one that looks like a piece of paper with a plus sign will add a new file.

   .. admonition:: Tip

      The Explorer pane is in the sidebar is called the activity panel. If yours doesn"t appear automatically, 
      open it from *View -> Appearance -> Show Activity Bar*. The Explorer is the top option on the activity bar.
      There are a few other options in the activity bar that we will be checking out throughout the course!

#. When you create a new file, it should open up automatically in the editor space in the center of the screen. If it doesn't, you simply click on ``main.py`` in the Explorer pane to open it up.
#. Add a ``print`` statement to your file that will output a greeting.
#. Now we need to run our code! This is why we needed the Python extension. Go ahead and open up the *Run and Debug* menu in the activity panel.

   .. figure:: figures/vsc-run-and-debug.png
      :alt: Run and Debug menu in Visual Studio Code

#. Click on on the *Run and Debug* option and search for *Python File Debug currently active file*.

   .. figure:: figures/vsc-run-and-debug-select.png
      :alt: Top bar with option to run current file selected.

#. When you run the file, a window pops up at the bottom of the screen with the output.

   .. figure:: figures/vsc-run-and-debug-output.png
      :alt: Output from running the code in index.py

   This is just an example of what the output might look like. You should see whatever greeting you put inside your ``print`` statement.

If you successfully ran your code, your Visual Studio Code setup is ready to go!


