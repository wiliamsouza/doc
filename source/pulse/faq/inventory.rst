Inventory Server
================

How do I inject inventories off-site?
-------------------------------------

.. note:: #TODO: Migrate and link here.

Just use the furnished script:

Ensure that::

  libxml-simple-perl and libwww-perl

Are installed on the server ocs inventory agent is installed on target.

Collect a inventory on the target::

  target:/tmp# ocsinventory-agent --local=/tmp
  [info] Accountinfo file doesn't exist. I create an empty one.
  [info] Inventory saved in /tmp/target-2010-08-17-17-05-53.ocs

Put inventory on the server.

Inject inventory from the server::

  server:/tmp# Ocsinventory_local.pl --file target-2010-08-17-17-05-53.ocs --urlhttp://127.0.0.1:9999 --debug
  Loading target-2010-08-17-17-05-53.ocs
  200 OK
  Response from server:
  <?xml version="1.0" encoding="utf-8" ?><REPLY><RESPONSE>no_account_update</RESPONSE></REPLY>
