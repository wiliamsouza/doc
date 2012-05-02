======================
MMC release guidelines
======================

This document explains how to release a new MMC core version.

MMC Core release components
###########################

What we release is a single tarball called mmc-core-VERSION.tar.gz.

This tarball contains:

- the MMC agent, the core MMC modules (audit framework) and
  the core plugins "base" and "ppolicy"

- the MMC web interface framework, with the "base" and "ppolicy" web
  modules.

Release Requirements
####################

Beware that mmc-agent requirements must be met before mmc-web-* one.

Requirements for the MMC agent (mmc-core/agent)
===============================================

Please check the requirements in the given order.

The Changelog file must be updated. If an entry in the changelog is a bugfix
of a bug reported in the bug tracking system, the ticket number must be written.

The default shipped configuration files are updated if needed (a new
option is available in a plugin or the MMC agent for example).

For the agent and each plugin, the VERSION attribute must be updated to the
version number we release, in those files:
:file:`mmc/agent.py mmc/plugin/base/__init__.py mmc/plugin/ppolicy/__init__.py`.

For each plugin, the APIVERSION attribute may be updated. The APIVERSION
string is similar to libtool library versions: current:revision:age.

- current : The most recent interface number that this library implements.
- revision : The most recent interface number that this library implements.
- age : The difference between the newest and oldest interfaces that this
  library implements. In other words, the library implements all the interface
  numbers in the range from number current - age to current.

Here are a set of rules to update the APIVERSION string:

#. If a Python plugin source code has changed at all since the last release,
   then increment revision (c:r:a becomes c:r+1:a)
#. If any interfaces have been added, removed, or changed since the last
   release, increment current, and set revision to 0
#. If any interfaces have been added since the last release, then increment age
#. If any interfaces have been removed since the last public release,
   then set age to 0.

All the python unit tests runs succesfully.

Requirements for the MMC web interface
======================================

Please check the requirements in the given order.

The Changelog file must be updated. If an entry in the changelog is a bugfix
of a bug reported in the bug tracking system, the ticket number must be written.

The default shipped ``mmc.ini`` configuration file is updated if needed.

The version attribute contained in each ``infoPackage.inc.php`` file of each
web modules ("base" and "ppolicy") must be updated to the version we release,
thanks to the setVersion method.

Each web module must be able to interact with their corresponding MMC agent
plugin we are going to release. For example, the "base" web module must be
compatible with the "base" plugin of the MMC agent. The APIVersion variable
contained in each ``infoPackage.inc.php`` file of each web modules must be
equal to the APIVERSION attribute of the corresponding MMC agent python plugin.
This is done thanks to the setAPIVersion method.

Each new page or field of the web interface must be protected by an ACL.

The web selenium tests are successful with the MMC agent revision we are going
to release and that met the release requirement.

The manual tests of the web interface are successful.

Documentation update
####################

All the installation/configuration manuals must be updated and checked.

The Python API documentation must be regenerated. (This is done automatically every day.)

The PHP API documentation must be regenerated. (This is done automatically every day.)

The upgrade procedure is updated: http://mds.mandriva.org/wiki/UpgradeProcedure.

Trac update
###########

Via trac-admin, a new version number must be added to the project,
associated with a release date.

::

    # trac-admin .
    # version add "MMC-CORE X.Y.Z" "Jul 27, 2006"
    # quit

If this release adds a new component, it must be added to the project.

::

    # trac-admin .
    # component add mmc-component-name
    # quit

Making the mmc-core tarball
###########################

The :file:`mmc-core/trunk` directory of the SVN repository is tagged into
:file:`mmc-core/tags` according to the version number of the release.
The tag format is MMC-CORE_x_y_z. For example, if the version we release is
1.2.3, the tag is MMC-CORE_1_2_3.

The version is updated in the :file:`configure.ac` file, then a
tarball called mmc-core-x.y.z.tar.gz is created using the ``make dist``
command.

Publishing the release
######################

The tarballs are put in the public download place.

The debian packages repository is updated, for Lenny and Squeeze.

The RPMs packages repository for Mandriva MES5 and Mandriva Cooker are
updated.

The demo VMware image is updated thanks to the RPM packages.

A mail is sent to the mds-announce mailing list.

The freshmeat entry is updated.
