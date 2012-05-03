===================
Quick install guide
===================

The MMC, MDS and Pulse source code share the same installation script. This
mean that the MMC always will be installed when installing from source code.
You can disable MDS or Pulse at configuration time.

Packages naming conventions
===========================

Here are the packages naming conventions:

* mmc-agent: the MMC agent package
* python-mmc-``PLUGIN``: MMC agent plugin
* mmc-web-``PLUGIN``: web interface plugin

Where ``PLUGIN`` can be one of :doc:`mail </mds/plugins/mail>`, :doc:`network 
</mds/plugins/network>`, :doc:`samba </mds/plugins/samba>` and :doc:`sshlpk
</mds/plugins/sshlpk>`.

Sample configuration files
==========================

All related sample configuration files are available in the python-mmc-base
package, in the directory :file:`/usr/share/doc/python-mmc-base/contrib/`
or on our repository_.

You will find there OpenLDAP, SAMBA and Postfix configuration files and also
OpenLDAP schemas.

.. _repository: https://github.com/mandriva-management-console/mmc/tree/master/base/agent/contrib/

Instalation options
===================

There are three easy options to install:

* Install an :doc:`official release from source tarball</install/release>`.

* Install a version provided by your :doc:`operating system distribution 
  </install/distribution>`.

* Install the latest :doc:`development </install/development>` version.

