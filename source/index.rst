.. Mandriva Management Console documentation master file, created by
   sphinx-quickstart2 on Fri Apr 13 10:26:35 2012.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Mandriva management console
===========================

Mandriva Management Console(MMC) is a framework used by Mandriva Directory
Server(MDS) and Pulse 2 projects that provides plugins for MMC.

MMC is made of two parts:

* An agent running on the machine to manage. We call it MMC agent.
  The agent exports to the network several plugins that allow to manage the
  machine. Of course, there can be multiple agents running on the network.
  The agent and its plugins are written in Python.

* A web interface, that talks to the agent(s) using XML-RPC.
  The interface is written in PHP, and use the scriptaculous and prototype
  frameworks to provide an AJAX experience across all major browsers.

The MMC provides 3 plugins:

* base: a plugin for managing users and groups in LDAP
* ppolicy: a plugin for managing user password policies
* audit: a framework for recording all operations done in the MMC interface

.. note:: Other plugins are part of MDS and pulse2 projects.

:doc:`Community </mmc/community>`
  How keep in touch.

:doc:`Roadmap </mmc/roadmap>`
  Where we are going to

:doc:`FAQ </mmc/faq>`
  Frequent asked questions.

Mandriva directory server
=========================

Mandriva Directory Server is an open source enterprise directory platform
based on LDAP designed to manage identities, access control informations,
policies, application settings and user profile.

MDS is composed of the following plugins:

* samba: The samba plugin allows the MMC to add/remove SAMBA attributes to
  users and groups and manage samba share.

* network: The network plugin allows the MMC Python API to manage DNS zones
  and hosts, DHCP subnet and hosts, into a LDAP. Patched version of ISC BIND
  with LDAP backend support and ISC DHCP with LDAP configuration file backend
  support are needed. PowerDNS support is also available. 

* mail: The mail plugin allows the MMC to add/remove mail delivery management
  attributes to users and groups, and mail virtual domains, mail aliases.
  Zarafa support is also available.

* sshlpk: The sshlpk plugin allows the MMC to manage lists of SSH public keys
  on users.

* userquota: The userquota plugin allows the MMC to set filesystem quotas to
  users. The plugin provides LDAP attributes for storing quota information.
  The plugin allows also to store network quotas in the LDAP directory for
  external tools.

:doc:`Community </mds/community>`
  How keep in touch.

:doc:`Roadmap </mds/roadmap>`
  Where we are going to

:doc:`FAQ </mds/faq>`
  Frequent asked questions.

Pulse 2
=======

Pulse 2 is an Open Source tool that simplifies application deployment,
inventory, and maintenance of an IT network. It provides useful features to
rescue disk image to restore a unique computer or image to be deployed
across the whole computers network. Remote application deployment and
updates. Software and hardware inventory, remote diagnostic and control. 

:doc:`Community </pulse/community>`
  How keep in touch.

:doc:`Roadmap </pulse/roadmap>`
  Where we are going to

:doc:`FAQ </pulse/faq/index>`
  Frequent asked questions.

More
====

:doc:`Development </development>`
  How to set up a development enviroment.

