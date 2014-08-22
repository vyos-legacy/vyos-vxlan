VXLAN-VYOS
==========

vxlan-vyos is CLI extension for virtual extensible LAN interface on VyOS(http://vyos.net). This CLI extension can be applied on VyOS helium later (kernel version issue).


How to install
==============

	 git clone http://github.com/upa/vxlan-vyos.git
	 cd vxlan-vyos
	 sudo cp -r vyatta-cfg /opt/vyatta/share/
	 sudo cp -r vyatta-op /opt/vyatta/share/
	 echo vxlan vxlan > /opt/vyatta/etc/netdevice.d/vxlan

How to use
==========

	 
	 interfaces {
	     ethernet eth0 {
	         address dhcp
	     }
	     loopback lo {
	     }
	     vxlan vxlan0 {
	         group 239.0.0.1
	         vni 0
	     }
	 }
	 
And, you can set _dev_ in _vxlan vxlanX_, but change of _dev_ state requires
delete/create vxlan interface.


ToDo
====
- some configurations under _interfaces vxlan vxlanX_
- some vxlan attributes (e.g, l2miss, l3miss and more)
- push to vyos repo ?


Contact
=======
upa@haeena.net
