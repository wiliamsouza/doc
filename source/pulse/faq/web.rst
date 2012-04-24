Web Interface
=============

I'm getting an error while creating bundles, but other deployments work.
-----------------------------------------------------------------------

If Suhosin is installed and activated on your web server, make sure than
request.max_varname_length and post.max_name_length are set to at least 160::

  suhosin.request.max_varname_length = 160
  suhosin.post.max_name_length = 160

You can also activate Suhosin's simulation mode with this flag, and requests
will no more be blocked::

  suhosin.simulation = On
  Update / Upgrade

I just saw that a new version just came out, what do I have to fear from?
-------------------------------------------------------------------------

Please see our upgrade instructions.

How do I follow a particular version?
-------------------------------------

Generally speaking, all repositories are including a keyword standing the
version. For exemple:

.. note:: #TODO: Migrate and link here.

MES 5 / 64 bits / stable version : http://pulse2.mandriva.org/pub/pulse2/server/mandriva/mes5/x86_64/ stable
RHEL 5 / 32 bits / version 1.2.1 : http://pulse2.mandriva.org/pub/pulse2/server/redhat/$releasever/$basearch/ 1.2.1
