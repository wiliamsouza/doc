TFTP Setup
==========

Debian::

    # apt-get install atftpd atftp

Using dpkg-reconfigure debconf will ask you for:

* Should the server be started by inetd?: Choose <No>.
* Port to listen for tftp request: Accept the default value. 
* Retry timeout: Accept the dafault value. 
* Maximum number of threads: Accept the default value.
* Enable 'timeout' support? Choose <Yes>.
* Enable 'tsize' support? Choose <Yes>.
* Enable 'block size' support? Choose <Yes>.
* Enable multicast support? <Yes>
* Port range for multicast file transfer: Accept the default value.
* Address range for multicast transfer: Accept the dafault value.
* TTL for multicast packets: Accept the default value.
* Verbosity level: Accept the default value.
* Base directory: Change to /var/lib/pulse2/imaging.
* Log to file instead of syslog? Choose <Yes>.
* Log file: Accept the default value.

CentOS::

    # yum

Mandriva::

    # urpmi

Bootloader and kernel are served to the client with TFTP protocol.
We recommend using the atftpd server as it supports multicast..

You must configure the TFTP server to use as base directory::

   /var/lib/pulse2/imaging/

.. Note:: don't use inetd.

Then check the configuration::

    # atftp localhost
    tftp> get /bootloader/pxe_boot
    tftp> quit
    # rm pxe_boot

