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

Extensions and Themes
---------------------

One of the great things about Visual Studio Code is that it is highly-customizable.
You can add extensions to work with specific languages or change the color theme to one that suits you better!

Required Extensions
^^^^^^^^^^^^^^^^^^^

For this class, you will need to add the following extensions to Visual Studio Code:

#. `Python <https://marketplace.visualstudio.com/items?itemName=ms-python.python>`

   .. admonition:: Note

      In order for this extension to work properly, you need to have followed the steps to :ref:`install Python <python-system-install>` on your machine.

#. `Github Pull Requests and Issues <https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github>`

   .. admonition:: Note

      This extension requires you to authorize access to your Github account.

Optional Extensions
^^^^^^^^^^^^^^^^^^^

As you code more, you may find new tools and extensions you want to add to Visual Studio Code. It is your local development environment, so configure away!
Even a simple change like switching up the themes to different colors to make your coding life easier!