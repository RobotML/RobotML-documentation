.. _DG_IFD_SVN:

Install and use :term:`SVN`
---------------------------

SVN is the tool chosen in the *Formal Robotician portal* to store and retrieve information (Problem, scenario, code, ...).
We indicate here how to install it on the reference platform (UBUNTU) and then provide some of the commands that can be used directly in a terminal to interact with the repository IF you have access credentials.

Install SVN (Ubuntu)
````````````````````

``sudo apt-get install subversion``

`Open in Software Center <http://apt.ubuntu.com/p/subversion>`__

Get the workspace from a server with your login
```````````````````````````````````````````````

This means to download on your own computer a copy of part of whole of the repository in the frame of what your credentials open.

::

    svn checkout --username USERNAME URI LOCALDIR

Update your local copy
``````````````````````

One of the great advantage of this type of tools is to allow their user to synchronise the different changes applied by others very easily.
It is not to be afraid to lose any of the development done locally as the tool will discover eventually discrepancies and offers you merging facilities if needed.

::

    svn update

Commit your changes to the server
`````````````````````````````````

If you need to upload part or whole of your work, then do it. You can always commit (meaning upload on the portal) not finished work.
It is of no importance as :term:`users <user>` of the repository will always be able to revert to a working copy notwithstanding the capability to use the branching facility.

::

    svn commit

More information
````````````````

This small document is of high value to help you using SVN.

.. figure:: RevisitOfDistributionInstallation_images/svnbook.gif
   :align: center
   :alt: svn-book

   `svnbook.red-bean.com <http://svnbook.red-bean.com/en/1.7>`__