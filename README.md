ntp
===

This role enables users to install and configure ntp on their hosts.

Requirements
------------

This role requires Ansible 1.4 or higher, and platform requirements are listed
in the metadata file.

Role Variables
--------------

The variables that can be passed to this role and a brief description about
them are as follows. See the NTP configuration documentation for details:

	# The driftfile
	driftfile: /var/lib/ntp/drifta

	# The server to sync time with
	server: [0.ubuntu.pool.ntp.org, 1.ubuntu.pool.ntp.org]

	restrict:                                                           
	  - "restrict -4 default kod notrap nomodify nopeer noquery"
	  - "restrict -6 default kod notrap nomodify nopeer noquery"
	  - "restrict 127.0.0.1"

	crypto: no
	includefile: no
	keys: no
	trustedkey: no
	requestkey: no
	controlkey: no
	statistics: no
	broadcast: no
	broadcastclient: no
	multicastclient: no

Examples
--------

1) Install ntp and set the default settings.

	- hosts: all
	  roles:
	    - role: ntp

2) Install ntp and set some custom servers.

	- hosts: all
	  roles:
	    - role: ntp
	      server: [2.ubuntu.pool.ntp.org, 1.ubuntu.pool.ntp.org]

Dependencies
------------

None

License
-------

BSD

Author Information
------------------

Benno Joy

