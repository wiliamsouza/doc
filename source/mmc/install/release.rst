===============================
Installation from source tarbal
===============================

.. include:: /mmc/install/requirements.rst


Get the source code
===================

Get the current tarball at this URL: ftp://mds.mandriva.org/pub/mmc-core/sources/current/

::

    # tar xzvf mmc-core-x.y.z.tar.gz
    # cd mmc-core-x.y.z
    # ./configure --sysconfdir=/etc --localstatedir=/var
    # make
    # make install
    # tar xzvf mds-x.y.z.tar.gz
    # cd mds-x.y.z
    # ./configure --sysconfdir=/etc --localstatedir=/var
    # make
    # make install

The default $PREFIX for installation is :file:`/usr/local`. You can change it
on the ``./configure`` line by adding the option ``--prefix=/usr`` for example.

Here are how the files are installed:

* :file:`$PREFIX/sbin/mmc-agent`: the MMC agent
* :file:`$PREFIX/lib/mmc/`: helpers for some MMC plugins
* :file:`/etc/mmc/`: all MMC configuration files. There files are sample files
  you will need to edit.
* :file:`/etc/init.d/mmc-agent`: MMC agent init script
* :file:`$PREFIX/lib/pythonX.Y/site-packages/mmc`: MMC Python libraries and
  plugins.
* :file:`$PREFIX/lib/pythonX.Y/site-packages/mmc/plugins/`: MMC Python plugins
* :file:`$PREFIX/share/mmc/`: all MMC web interface related files
  (PHP, images, ...l)
* :file:`$PREFIX/share/mmc/modules/`: MMC web interface plugins
* :file:`/etc/mmc/mmc.ini`: MMC web configuration file

To keep your configuration files intact you may change the configure line to::

    $ ./configure --prefix=/usr --sysconfdir=/etc --localstatedir=/var --disable-conf 

The option ``--disable-conf`` will disable configuration files installation.

.. include:: /mmc/install/ldap.rst

.. include:: /mmc/install/mysql.rst

.. include:: /mmc/install/apache.rst

.. include:: /mmc/install/config.rst
