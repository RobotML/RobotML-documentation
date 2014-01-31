.. _DG_IFD_RODI:

Revisit of :term:`RobotML-sdk` Installation
------------------------------------------

What was presented in the user guide, is now detailed for each of the component and using the manual installer.
Other tools installation are detailed and are associated to page of their own as indicated.

Installer
`````````

Run ``proteus.run`` in:

-  `svn-wp2/trunk/S2.3.4-PROTEUS-Distribution/install/proteus.run <https://dassault3.ddo.net/svn/proteus-wp2/trunk/S2.3.4-PROTEUS-Distribution/install/proteus.run>`__

with the following command in a terminal (do not ``sudo``):

::

    sh proteus.run

You will need to provided you login and password for the `repository <https://packages.greyc.fr/proteus>`__. And your root pass as well to install the packages.

*nb*: in case of download or network failure, you can restart this script when you want. It will overwrite the configuration without re-downloading what was already done.


Installation tool: Run in Terminal
::::::::::::::::::::::::::::::::::

.. figure:: RevisitOfDistributionInstallation_images/Screenshot0runterm.png
   :width: 600px
   :align: center
   :alt: install-runterm

   Click on "``Run in Terminal``"


Installation tool: login
::::::::::::::::::::::::

.. figure:: RevisitOfDistributionInstallation_images/Screenshot1login.png
   :width: 600px
   :align: center
   :alt: install-login

   Login and password for `the repository <https://packages.greyc.fr/proteus>`__


Installation tool: next
:::::::::::::::::::::::

.. figure:: RevisitOfDistributionInstallation_images/Screenshot2loginnext.png
   :width: 600px
   :align: center
   :alt: install-loginnext

   Next...


Installation tool: choose apps
::::::::::::::::::::::::::::::

.. figure:: RevisitOfDistributionInstallation_images/Screenshot3selectapp.png
   :width: 600px
   :align: center
   :alt: install-selectapp

   Choose your packages


Installation tool: install
::::::::::::::::::::::::::

.. figure:: RevisitOfDistributionInstallation_images/Screenshot4install.png
   :width: 600px
   :align: center
   :alt: install-install

   Install...


Installation tool: checking password
::::::::::::::::::::::::::::::::::::

.. figure:: RevisitOfDistributionInstallation_images/Screenshot5checklogin.png
   :width: 600px
   :align: center
   :alt: install-checklogin

   Checking your password for `packages.greyc.fr/proteus <https://packages.greyc.fr/proteus/>`__


Installation tool: root
:::::::::::::::::::::::

.. figure:: RevisitOfDistributionInstallation_images/Screenshot6rootpw.png
   :width: 600px
   :align: center
   :alt: install-rootpw

   Give your ``root`` password (aka. super user)


Demo / Tests
````````````

A MORSE presentation containing examples and video is available at: `bit.ly/proteus2 <http://bit.ly/proteus2>`__

.. figure:: RevisitOfDistributionInstallation_images/demo-slides.png
   :width: 600px
   :align: center
   :alt: demo-slides

   :ref:`MORSE & ROS HOWTO <UG-PI-IPD>`


Installation: Eclipse
`````````````````````

version: Eclipse Modeling Indigo (3.7) & Papyrus 0.8.2

::

    sudo apt-get install proteus-base-eclipse

`Open proteus-base-eclipse in Software Center <http://apt.ubuntu.com/p/proteus-base-eclipse>`__

Test install
::::::::::::

Run the following command in a terminal:

::

    eclipse

Update
::::::

.. figure:: RevisitOfDistributionInstallation_images/screen-eclipse-update.png
   :width: 600px
   :align: center
   :alt: eclipse-update

   eclipse-update


Installation of frameworks
``````````````````````````

Installation: CycabTK
:::::::::::::::::::::

version: 2.0

``sudo apt-get install proteus-cycabtk``

`Open CycabTK in Software Center <http://apt.ubuntu.com/p/proteus-cycabtk>`__

Test install
''''''''''''

Run the following command in a terminal:

::

    mgengine

Then, in ``mgengine`` console

::

    require "tutorial"

Which should display a vehicle with a camera, a laser scanner and two infrared sensors.


Installation: MORSE
:::::::::::::::::::

version: 0.4

``sudo apt-get install proteus-morse``

`Open in Software Center <http://apt.ubuntu.com/p/proteus-morse>`__

Test install
''''''''''''

Run the following command in a terminal:

::

    morse check

see `MORSE README <https://github.com/laas/morse#readme>`__


Installation: RTMaps
::::::::::::::::::::

version: 4.0.1

``sudo apt-get install proteus-rtmaps``

`Open in Software Center <http://apt.ubuntu.com/p/proteus-rtmaps>`__

Test install
''''''''''''

Run the following command in a terminal:

::

    rtmaps /opt/rtmaps/samples/demo_lidar_linux.rtd

.. figure:: RevisitOfDistributionInstallation_images/demo_rtmaps.png
   :width: 600px
   :align: center
   :alt: demo-rtmaps

   `RTMaps demo <http://intempora.com/technology/rtmaps-software>`__


Installation: Urbi
::::::::::::::::::

version: 2.7.1

``sudo apt-get install proteus-urbi``

`Open in Software Center <http://apt.ubuntu.com/p/proteus-urbi>`__


Installation: VLE
:::::::::::::::::

version: 1.0

``sudo apt-get install proteus-vle``

`Open in Software Center <http://apt.ubuntu.com/p/proteus-vle>`__


Installation: Orocos
::::::::::::::::::::

version: 0.4

``sudo apt-get install proteus-orocos``

`Open in Software Center <http://apt.ubuntu.com/p/proteus-orocos>`__


Installation: Effibox
:::::::::::::::::::::

version: XXX

``sudo apt-get install proteus-aroccam``

`Open in Software Center <http://apt.ubuntu.com/p/proteus-aroccam>`__


Installation: Protege
:::::::::::::::::::::

version: 4.1

``sudo apt-get install proteus-base-protege``

`Open in Software Center <http://apt.ubuntu.com/p/proteus-base-protege>`__


Update the distribution
```````````````````````

First, you need to update the repositories list:

::

    sudo apt-get update

Then, upgrade your packages:

::

    sudo apt-get upgrade


Remove a package
::::::::::::::::

::

    sudo apt-get remove vle

and autoremove to clean the former dependencies:

::

    sudo apt-get autoremove


:term:`SVN`
```````````

This asset is mandatory for accessing *Formal Robotician portal* elements.
Some assets can be accessed directly through the portal itself.

Specific documentation can be found following this :ref:`link <DG_IFD_SVN>`\ .

.. TODO
	precise portal address

Proxy
`````

To update root's proxy settings:

::

    sudo gnome-network-properties

or see ``sudo -i``:

::

    The -i (simulate initial login) option runs the shell specified in the
    passwd(5) entry of the target user as a login shell.  This means that
    login-specific resource files such as .profile or .login will be read by
    the shell.  If a command is specified, it is passed to the shell for
    execution.  Otherwise, an interactive shell is executed.  sudo attempts to
    change to that user's home directory before running the shell.  It also
    initializes the environment, leaving DISPLAY and TERM unchanged, setting
    HOME, MAIL, SHELL, USER, LOGNAME, and PATH, as well as the contents of
    /etc/environment on Linux and AIX systems.  All other environment
    variables are removed.

or with ``pip --proxy``:

::

    sudo pip install --proxy=http://myproxy:8080 -U rosinstall


That's all Folks!
`````````````````

short link to this presentation: `bit.ly/proteus1 <http://bit.ly/proteus1>`__

.. figure:: RevisitOfDistributionInstallation_images/proteus1.qrcode.png
   :align: center
   :alt: proteus-install

1 page doc: `bit.ly/proteus1md <http://bit.ly/proteus1md>`__

sources on GitHub: `bit.ly/proteus-src <http://bit.ly/proteus-src>`__
