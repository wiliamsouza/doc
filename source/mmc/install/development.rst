==================================
Installing the development version
==================================

This how to will guide you through the installation and configuration of Pulse2
development environment

.. include:: /mmc/install/requirements.rst

Get the source code
-------------------

The development source code is managed in github https://github.com/mandriva-management-console/mmc.

Clone the github repository::

    $ git clone git://github.com/mandriva-management-console/mmc.git

To compile and install all modules run::

    $ ./autogen.sh
    $ ./configure --prefix=/usr --sysconfdir=/etc --localstatedir=/var
    $ make
    # make install

You can disable MDS or Pulse module installation using:

* ``--disable-mds``: Do not install MDS set of modules.
* ``--disable-pulse2``: Do not install Pulse2 set of modules.

You can update by running the following command::

    $ git pull origin master

To keep your configuration files intact you may change the configure line to::

    $ ./configure --prefix=/usr --sysconfdir=/etc --localstatedir=/var --disable-conf 

The option ``--disable-conf`` will disable configuration files installation.


.. include:: /mmc/install/ldap.rst

.. include:: /mmc/install/mysql.rst

.. include:: /mmc/install/apache.rst

.. include:: /mmc/install/config.rst
