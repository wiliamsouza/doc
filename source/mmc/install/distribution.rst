===========================================
Platform-specific installation instructions
===========================================

How to install the Mandriva Management Console provided by a third-party
Linux distributors.

Mandriva
========

Mandriva users are lucky because packages for the MDS and the MMC are available.

Packages for Mandriva 2010.0, 2010.2, 2011.0 and Cooker are available on
official repositories. You will find an official mirror `here <http://api.mandriva.com/mirrors/list.php>`_.

You can also add the repositories with the following command::

    urpmi.addmedia --distrib --mirrorlist '$MIRRORLIST'

To install the MMC base packages, just type::

    # urpmi mmc-agent mmc-web-base python-mmc-base

Debian
======

For Debian Lenny, add this in your sources.list::

    deb http://mds.mandriva.org/pub/mds/debian lenny main

For Debian Squeeze::

    deb http://mds.mandriva.org/pub/mds/debian squeeze main

To install MMC base packages, just type::

    # apt-get update
    # apt-get install mmc-agent mmc-web-base python-mmc-base


Fedora, CentOS, OpenSUSE and Red Hat
=====================================

We also provide packages for this distributions trough OpenBuildSystem here:

- `MMC core <http://software.opensuse.org/download.html?project=home:eonpatapon:mds&package=mmc-core>`_
- `MDS plugins <http://software.opensuse.org/download.html?project=home:eonpatapon:mds&package=mds>`_

.. note:: CentOS DAG repository

   For some packages, you will need to add the DAG repository to yum. Create
   a file named :file:`/etc/yum.repos.d/DAG.repo` containing::

       # DAG Repository for RedHat Enterprise 4 / CentOS 4
       [dag]
       name=DAG Repository
       baseurl = http://apt.sw.be/redhat/el$releasever/en/$basearch/dag
       gpgkey=http://dag.wieers.com/packages/RPM-GPG-KEY.dag.txt
       gpgcheck=1
       enabled=0
