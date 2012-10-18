
VirtualBox
==========

If you install PROTEUS tools through a virtual machine, remember that 3D simulation software wont work well since they need OpenGL, which is not supported by VirtualBox. You will need to change some default settings:

-  Activate PEA/NX
-  Activate 3D acceleration
-  Add video memory

Once Ubuntu installation is over, go to "Devices > Install the Guest Additions", then activate the VirtualBox video driver.

Use the tool ``/usr/bin/jockey-gtk`` to install additional drivers.

In MORSE, it is recomanded to use the "WIREFRAME" mode for your simultaion. cf. `morsebuilder.py#L401 <https://github.com/laas/morse/blob/0.5.1/src/morse/builder/morsebuilder.py#L401>`__:

::

    env.set_viewport(viewport_shade = 'WIREFRAME')


Settings
````````

.. figure:: VirtualBox_images/vb1.png
   :align: center
   :alt: vb-settings


PEA/NX
``````

.. figure:: VirtualBox_images/vb2.png
   :align: center
   :alt: vb-peanx


3D
``

.. figure:: VirtualBox_images/vb3.png
   :align: center
   :alt: vb-3d

