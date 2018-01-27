Modifying the Kernel
====================

A brief how-to

This talk will not:
-------------------

.. figure:: static/nope-society6.jpg
	:align: center
	:height: 550px

This talk will:
---------------

.. figure:: static/yes-man1.jpg
	:align: center
	:height: 550px

Your Environment:
-----------------

**Build Appliance**

.. figure:: static/tux-svg.png
	:align: left
	:height: 200px

.. figure:: static/apple-logo.gif
	:align: right
	:height: 200px

.. figure:: static/windows-logo.png
	:align: center
	:height: 200px

Yocto
-----

.. figure:: static/venus.jpg
	:align: center
	:height: 550px

Quick EMUlator
--------------

.. figure:: static/Emu-wild.jpg
	:align: center
	:height: 550px

Building the Kernel
-------------------

.. figure:: static/bob-the-builder.jpeg
	:align: center
	:height: 550px

// To Install
-------------

* git
* ``git clone git://git.yoctoproject.org/linux-yocto-3.14``
* The qemu you need (if not sure, ``uname -m``)
* make, gcc, 

// TODO
-------

* ``make defconfig`` (`options`_)
* ``make``
* Boot the VM using your compiled kernel
* ``qemu-system-x86_64 qemu-system-x86_64 -nographic -kernel ./arch/x86_64/boot/bzImage -enable-kvm -net none -usb -localtime --no-reboot --append "root=/dev/vda rw console=ttyS0 debug".``  

Demo Time
=========

Making your changes
-------------------

.. figure:: static/BowieChanges.png
	:align: center
	:height: 550px

// TODO
-------

* Make yo' changes
* Add ``$name.o`` to the appropriate Makefile
* Add to appropriate config file (ie. ``Kconfig.iosched``)
* Recompile and boot VM

Do that Demo
============

Testing
-------

.. figure:: static/qaengineer.png
	:align: center

Damn, dat Demo
==============

Creating a patch
----------------

* ``git diff origin/master > mypatch.patch``

.. figure:: static/pirate-eye-patch.jpg
	:align: center
	:height: 550px

Resources
---------

- `Yocto Kernel download`_
- `Yocto project documentation`_
- `Qemu booting options`_

Questions
---------

.. figure:: static/any-questions.gif
	:align: center
	:height: 550px

Thank you!
==========

.. _options: http://www.linux.org/threads/the-linux-kernel-configuring-the-kernel-part-1.4274/
.. _Yocto Kernel download: http://git.yoctoproject.org/
.. _Yocto project documentation: https://www.yoctoproject.org/documentation
.. _Qemu booting options: http://wiki.qemu.org/download/qemu-doc.html
