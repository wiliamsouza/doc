Basic MMC configuration
=======================

You can skip this part if plan to install pulse2. pulse2-setup take care of
mmc configuration to you.

Edit /etc/mmc/plugins/base.ini and change baseDN, password to meet your ldap
configuration.

Create a directory /home/archives::

    # mkdir /home/archives

Restart mmc-agent::

    # /etc/init.d/mmc-agent start 

At this point you can access mmc web interface::

    http://127.0.0.1/mmc/



Next steps
==========

Now you can install :ref:`mds` or :ref:`pulse`.
