==================================
Installing the development version
==================================

This how to will guide you through the installation and configuration of Pulse2
development environment

Installation form source code
=============================

Pre-requisites
--------------

Debian::

    # apt-get install git-core build-essential autogen autoconf libtool gettext
    python-sqlalchemy python-mysqldb python-ldap python-openssl
    python-twisted-web nsis xsltproc docbook-xsl 

Centos::

    # yum install git-core

Mandriva::

    # urpmi git-core

Get the source code
-------------------

The development source code is managed in github https://github.com/mandriva-management-console/mmc.

Clone the github repository::

    $ git clone git://github.com/mandriva-management-console/mmc.git

Compile and install::

    $ ./autogen.sh
    $ ./configure --prefix=/usr --sysconfdir=/etc --localstatedir=/var
    $ make
    # make install

You can update by running the following command::

    $ git pull origin master

To keep your configuration files intact you may change the configure line to::

    $ ./configure --prefix=/usr --sysconfdir=/etc --localstatedir=/var --disable-conf 

The option ``--disable-conf`` will disable configuration files installation.

OpenLDAP
=========

Debian::

    # apt-get install slapd ldap-utils

Debconf will ask only ldap root password by default to more granular configuration use::

    # dpkg-reconfigure slapd

Using dpkg-reconfigure debconf will ask you for:

    * Omit OpenLDAP server configuration?: Choose <No>.
    * DNS domain name: Enter you domain name.
    * Organization name: Enter organization name.
    * Admin password: Enter a password and confirm in next screen.
    * Database backend to use: choose HDB.
    * Do you want the database to be removed when slapd is purged: Choose <No>.
    * Allow LDAPv2 protocol: Choose <NO>.

Centos::

    # yum install

Mandriva::

    # urpmi

Schema
------

#TODO: Talk more about openldap changes in config and schema new storage.

Copy mmc schema to your corrent directory::

    $ cp /usr/share/doc/python-mmc-base/contrib/ldap/mmc.schema .

Create a file mmc.conf with::

    include    mmc.schema

Create a folder schemas::

    $ mkdir schemas

Convert mcc.schema to ldif::

   $ slaptest -f mmc.conf -F schemas/

Edit mmc schema, remove {0} from dn:, cn: and add cn=schema,cn=config to dn ::

    dn: cn=mmc,cn=schema,cn=config
    objectClass: olcSchemaConfig
    cn: mmc

Remove the following lines at the bottom of that file::

    structuralObjectClass: olcSchemaConfig
    entryUUID: 0ec2fe60-1381-1031-8f21-f92982aeda45
    creatorsName: cn=config
    createTimestamp: 20120405153755Z
    entryCSN: 20120405153755.316520Z#000000#000#000000
    modifiersName: cn=config
    modifyTimestamp: 20120405153755Z

Add schema to ldap::

   # ldapadd -Y EXTERNAL -H ldapi:/// -f schemas/cn\=config/cn\=schema/cn\=\{0\}mmc.ldif

MySQL
=====

Debian:

    # apt-get install mysql-server

Debconf will ask mysql root password.

Centos::

    # yum install

Mandriva::

    # urpmi

Apache HTTP server
==================

Debian::

   # apt-get install apache2 php5 php5-gd php5-xmlrpc


Centos::

    # yum install

Mandriva::

    # urpmi

Configuring apache2 and php
---------------------------

Enable mmc web site::

    # ln -s /etc/mmc/apache/mmc.conf /etc/apache2/sites-enabled/mmc.conf

Restart apache2::

    # /etc/init.d/apache2 restart

Pulse setup
===========

pulse2-setup will ask::

    INFO     - Load defaults values from existing config
    INPUT    - Enable audit module (Y/n): y
    INPUT    - Enable inventory server (Y/n): y
    INPUT    - Enable imaging server (Y/n): y
    INPUT    - Enable package server (proxy) (Y/n): y
    INPUT    - Server external IP address (default: 10.0.2.15): 172.16.0.4
    INFO     - Run setup
    INPUT    - Database host (default: localhost): 
    INPUT    - Database admin user (default: root): 
    INPUT    - Database admin password: 
    ...
    INPUT    - LDAP uri (default: ldap://127.0.0.1:389):
    INPUT    - LDAP base DN (default: dc=mandriva, dc=com): 
    INPUT    - LDAP admin DN (default: cn=admin, dc=mandriva, dc=com): 
    INPUT    - LDAP admin password: 
    ...
    INPUT    - Wake-on-lan tool path (default: /usr/sbin/pulse2-wol):

DHCP
====

Debian::
   # apt-get install isc-dhcp-server


