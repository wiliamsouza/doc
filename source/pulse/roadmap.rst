=======
Roadmap
=======

1.0
===

* Use the MMC framework.
* Modularize all components to support a load increase (targeting 100 000+
  computers).
* Schedulers.
* Launchers
* Use  GLPI as a data backend.
* Get all computers available on the computing equipment.
* Get computers distribution inside the computing equipment (available in
  GLPI 0.70).
* Display logs about all software roll-out phases: transfer, execution and
  clean up.
* User interface works to support 100 000 computers (dynamic list with an
  AJAX filter).
* Packaging and install kit for RHEL 4, RHEL 5, Mandriva CS4, Debian Etch.
* User documentation.
* Official Pulse 2 community web site.

1.1
===

* Full SSL (TLS) support between components.
* Demons should be able to run under a non privileged user.
* Obfuscated passwords support in configuration files.
* Dynamic computers group using inventory content.
* Software traffic shaping on the targeted computers.

1.2
===

* Computers remote control with VNC (through an encrypted tunnel).
* Application chaining (Bundles).
* Local Proxy : kind of "Peer to Peer" mode (Former Pulse technology
  integration), and use a target computer as a temporary data repository.
* Display some GLPI inventory content.
* Display realtime data about a software deployment being done on a computers
  group.

1.2.1
=====

* Support for entities in inventory backend.
* New Local proxy mode to perform parallel uploads.
* Pulse 2 version 1.2.2.
* Enhanced cleanup mechanism for win32 plateforms.

1.2.3
=====

* Enforced scheduler.

1.2.4
=====

* GLPI 0.72 support.

1.2.5
=====

* GLPI 0.78/0.80 support.

1.3
===

* Global traffic shaping on all Pulse 2 components.
* Hard disk imaging and mastering (from the Linbox Rescue Server).
* Shared images management between computers.
* User interface works on the imaging and mastering module.
* User interface works on computers network boot menu.
* Computer image mastering on CD and DVD.
* Computer update according to a specified software profile and linked to a
  static computers group.

1.4
===

* RPM based Linux distribution deployment using the former Pulse technology.
* Debian based Linux distribution deployment.
* Package life cycle management, multi-sites package replication with traffic
  shaping, package versioning (depending on customer request).
* Inventory report.

1.5
===

* Use LDAP as a data backend.
