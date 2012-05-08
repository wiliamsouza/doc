.. Mandriva Management Console documentation master file, created by
   sphinx-quickstart2 on Fri Apr 13 10:26:35 2012.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.


===========
Get started
===========

This documentation holds information about three distinct projects:
:ref:`mmc` (MMC), :ref:`mds` (MDS) and :ref:`pulse`. MDS and Pulse2 are build on
top of MMC which works as base for MDS and Pulse2 plugins.

In order to install MDS or Pulse2 plugins you first need to install and 
configure :ref:`mmc`.

.. contents:: Table of Contents

.. _mmc:

Mandriva management console
===========================

Mandriva Management Console is a framework used by :ref:`mds` and :ref:`pulse` 
projects.

MMC is made of two parts:

* An agent running on the machine. The agent exports to the network several
  plugins that allow to remote manage the machine. Of course, there can be
  multiple agents running on the network. The agent and plugins are written
  in Python.

* A web interface, that controls the agent(s) using XML-RPC.
  The interface is written in PHP, and uses the scriptaculous and prototype
  frameworks to provide an AJAX experience across all major browsers.

The MMC provides 3 plugins:

* base: A plugin for managing users and groups in LDAP.

* :doc:`ppolicy </mmc/plugins/ppolicy>`: A plugin for managing user password
  policies.

* :doc:`audit </mmc/plugins/audit>`: A framework for recording all operations
  done in the MMC interface.

.. note:: Other plugins are part of :ref:`mds` and :ref:`pulse` projects.

:doc:`Installation </mmc/install/index>`
  Quick install guide.

:doc:`Community </mmc/community>`
  How to keep in touch.

:doc:`Roadmap </mmc/roadmap>`
  Where we are going to.

:doc:`FAQ </mmc/faq>`
  Frequently asked questions.

:doc:`Configuration files </mmc/config/index>`
  The reference documentation.

.. _mds:

Mandriva directory server
=========================

Mandriva Directory Server is an open source enterprise directory platform
based on LDAP designed to manage identities, access control informations,
policies, application settings and user profiles.

MDS is composed of the following plugins:

* :doc:`samba </mds/plugins/samba>`: The samba plugin allows the MMC to 
  add/remove SAMBA attributes to users and groups and manage samba shares.

* :doc:`network </mds/plugins/network>`: The network plugin allows the MMC
  Python API to manage DNS zones and hosts, DHCP subnets and hosts, into a LDAP.
  Patched version of ISC BIND with LDAP backend support and ISC DHCP with LDAP
  configuration file backend support is needed. PowerDNS support is also
  available.

* :doc:`mail </mds/plugins/mail>`: The mail plugin allows the MMC to
  add/remove mail delivery management attributes to users and groups, and mail
  virtual domains, mail aliases. Zarafa support is also available.

* :doc:`sshlpk </mds/plugins/sshlpk>`: The sshlpk plugin allows the MMC to
  manage lists of SSH public keys on users.

* userquota: The userquota plugin allows the MMC to set filesystem quotas to
  users. The plugin provides LDAP attributes for storing quota information.
  The plugin also allows to store network quotas in the LDAP directory for
  external tools.

:doc:`Installation </mds/install/index>`
  Quick install guide.

:doc:`Community </mds/community>`
  How keep in touch.

:doc:`Roadmap </mds/roadmap>`
  What's coming up next.

:doc:`FAQ </mds/faq>`
  Frequently asked questions.

:doc:`Configuration files </mds/config/index>`
  The reference documentation.

.. _pulse:

Pulse 2
=======

Pulse 2 is an Open Source tool that simplifies application deployment,
inventory, and maintenance of an IT network. It provides useful features to
create rescue disk images to restore a unique computer or image to be deployed
across the whole computers network. Remote application deployment and
updates. Software and hardware inventory, remote diagnostic and control. 

Pulse2 helps organizations with a range of a few computers to 100 000+ 
heterogeneous to inventory, maintain, update and take full control on their
IT assets. It's support for heterogeneous platforms includes MS Windows, 
GNU/Linux (Mandriva, Redhat, Debian, Ubuntu., etc.), Mac OSX, HP-UX, IBM AIX and
Solaris systems.

Pulse 2 is an easy-to-use, safe and flexible solution that allows you:

* Supervise large scale facilities through the use of a single Web interface
  console.

* Create and deploy hard disk images of your computers (new imaging module).

* Deploy new software and security updates on all your IT assets.

* Perform software and hardware inventory.

* Do remote diagnostics and remote management.

:doc:`Installation </mds/install/index>`
  Quick install guide.

:doc:`Community </pulse/community>`
  How to keep in touch.

:doc:`Roadmap </pulse/roadmap>`
  What's coming up next. 

:doc:`FAQ </pulse/faq/index>`
  Frequently asked questions.

:doc:`Configuration files </pulse/config/index>`
  The reference documentation.

More
====

:doc:`Development environment </install/development>`
  Installing the development version.

:doc:`Fork it </development/contributing>`
  Contributing using github.

:doc:`Scripts </development/scripts>`
  Writing scripts.

:doc:`Python module </development/python-module>`
  How to write a python module.

:doc:`PHP module </development/php-module>`
  How to write a PHP module.

:doc:`i18n and i10n </development/internationalization>`
  Internationalization and localization.

:doc:`Python style </development/python-code>`
  Style guide for python code.

:doc:`PHP style </development/php-code>`
  Style guide for PHP code.

:doc:`Release </development/release>`
  Release guidelines.

:doc:`Audit specification </mmc/specs/audit>`
  MMC audit framework specification.
