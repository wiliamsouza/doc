==================================
Installing the development version
==================================

In order to install Pulse2 and it's plugins you first need to install and
configure :ref:`mmc`.

This how to will guide you through the installation and configuration of Pulse2
development environment

.. include:: /pulse/install/requirements.rst

Get the source code
===================

The development source code is managed in github https://github.com/mandriva-management-console/mmc.

Clone the github repository::

    $ git clone git://github.com/mandriva-management-console/mmc.git

To compile and install all modules run::

    $ $ cd pulse2/
    $ ./autogen.sh
    $ ./configure --prefix=/usr --sysconfdir=/etc --localstatedir=/var
    $ make
    # make install

You can update by running the following command::

    $ git pull origin master

To keep your configuration files intact you may change the configure line to::

    $ ./configure --prefix=/usr --sysconfdir=/etc --localstatedir=/var --disable-conf 

The option ``--disable-conf`` will disable configuration files installation.

.. include:: /pulse/install/pulse-setup.rst

.. include:: /pulse/install/dhcp.rst

.. include:: /pulse/install/imaging.rst

.. include:: /pulse/install/nfs.rst

.. include:: /pulse/install/tftp.rst

