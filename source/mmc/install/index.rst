===================
Quick install guide
===================

The MMC, MDS and Pulse source code share the same installation script. This
mean that the MMC always will be installed when installing from source code.
You can disable MDS or Pulse at configuration time.

Pre-requisites
==============

This python modules are needed:

* python-twisted-web
* python-ldap
* pylibacl
* pyopenssl

The MMC web interface is written in PHP4. Basically, you just need to install
an Apache 2 server with PHP5 support. The XML-RPC module of PHP is needed too.

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

* Install an :doc:`official release from source tarball</mmc/install/release>`.

* Install a version provided by your :doc:`operating system distribution 
  </mmc/install/distribution>`.

* Install the latest :doc:`development </mmc/install/development>` version.

