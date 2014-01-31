Sphinx and RobotML documentation
--------------------------------

Documentation of this project is created thanks to the `Sphinx tool <http://sphinx.pocoo.org>`_. This tooling is using Python as its underlying framework. It means that it is indepedant of the platform on which you will work (It is more or less true, if you have any problems do send a mail to `Serge Stinckwhich <mailto:serge.stinckwhich@gmail.com>`_ in order to ask questions or provide bugs).

It is possible to download the complete Sphinx documentation in acrobat format following `http://sphinx.pocoo.org/sphinx.pdf <http://sphinx.pocoo.org/sphinx.pdf>`_.

Installation of Sphinx
^^^^^^^^^^^^^^^^^^^^^^

In order to install this tool, you have to:

1. Install *Python*\ : version used by the consortium is 2.7.3 considering documentation generation. You can download it from `here <http://www.python.org/download/releases/2.7.3>`_ choosing your own flavour. This version is verified but it does not mean the others are not working (we are speaaking here of the version 3 branch). 2. Install *Sphinx*\ : version used for generating documentation is 1.1.3. Hereafter a screenshot of the website indicating how to install.

.. figure:: images/SphinxInstall.png
   :align: center
   :alt: install-Sphinx

   *Install Sphinx*

How to generate with Sphinx
^^^^^^^^^^^^^^^^^^^^^^^^^^^

There is no graphical console allowing to push any buttons. It is needed to 

1. open a terminal (process is different with respect to the different OS) 2. verify you have access to sphinx command (PATH to complete and it depends also of the OS used) 3. change location in the folder tree in order to position to the root of the documentation (in PROTEUS distribution case on Linux, it means folder XXX) 4. type hereafter command (if -b option is forgotten, default is html, read `documentation  <http://sphinx.pocoo.org/sphinx.pdf>`_ for more information)

::

		sphinx-build -b html . destination_directory

5. you are now able to consider the result in the *destination_directory*

ECLIPSE RsT plugin
^^^^^^^^^^^^^^^^^^

It is possible to install an extension in the eclipse platform in order to manage Sphinx projects. You have to use the editor update site *http://resteditor.sourceforge.net/eclipse*  and then a RsT editor will be accessible. This plugin is not perfect but allows a management of the documentation projects in the same interface where everything else is done.

It is necessary to create a generic project and then create the build command (menu *project*/*properties*, then consider the *builders* choice in the left pane).


.. figure:: ./images/BuilderConfiguration-1.png
   :align: center
   :width: 400
   :alt:   Builders index choice

   *how to choose builders index*

It is necessary then to create the project customised builder (there is no possibility to do otherwise). Either you create the builder from scratch (use the New buider button) or you edit existing buider (use the edit button after selecting the builder to edit).


.. figure:: ./images/ImagesSphinx-1.png
   :align: center
   :width: 400
   :alt:   Create customised builder

   *how to create customised builder*

At this step, if you installed Sphinx, you are able to specify the command to launch when building the project. There are subtleties with respect to the different OS and what is shown concerns MacOS and Linux but is easily adaptable to Windows OS.

.. figure:: ./images/ImagesSphinx-2.png
   :align:  center
   :width:  700
   :alt:    builder configuration
   
   *how to customise builder* 