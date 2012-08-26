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
