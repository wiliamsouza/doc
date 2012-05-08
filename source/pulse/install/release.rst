===============================
Installation from source tarbal
===============================

Pre-requisites
==============

This python modules are needed for MMC to run:

- python-twisted-web
- python-ldap
- pylibacl
- pyopenssl

The MMC web interface is written in PHP4. Basically, you just need to install
an Apache 2 server with PHP5 support. The XML-RPC module of PHP is needed too.

Installation
============

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

- :file:`$PREFIX/sbin/mmc-agent`: the MMC agent
- :file:`$PREFIX/lib/mmc/`: helpers for some MMC plugins
- :file:`/etc/mmc/`: all MMC configuration files. There files are sample files
  you will need to edit.
- :file:`/etc/init.d/mmc-agent`: MMC agent init script
- :file:`$PREFIX/lib/pythonX.Y/site-packages/mmc`: MMC Python libraries and
  plugins.
- :file:`$PREFIX/lib/pythonX.Y/site-packages/mmc/plugins/`: MMC Python plugins
- :file:`$PREFIX/share/mmc/`: all MMC web interface related files
  (PHP, images, ...l)
- :file:`$PREFIX/share/mmc/modules/`: MMC web interface plugins
- :file:`/etc/mmc/mmc.ini`: MMC web configuration file
