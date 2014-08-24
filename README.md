VXLAN-VYOS
==========

vxlan-vyos is CLI extension for virtual extensible LAN interface on VyOS(http://vyos.net). This CLI extension can be applied on VyOS helium later (kernel version issue).


How to install
==============

	 git clone http://github.com/upa/vxlan-vyos.git
	 cd vxlan-vyos
	 sudo cp -r vyatta-cfg /opt/vyatta/share/
	 sudo cp -r vyatta-op /opt/vyatta/share/
	 sudo echo vxlan vxlan > /opt/vyatta/etc/netdevice.d/vxlan

How to use
==========

	 
	 interfaces {
	     bridge br0 {
	     }
	     ethernet eth0 {
	         address dhcp
	     }
	     loopback lo {
	     }
	     vxlan vxlan0 {
	         bridge-group {
	             bridge br0
		 }
		 group 239.0.0.1
	         vni 0
	     }
	     vxlan vxlan1 {
	         address 192.168.0.1/24
	         dev eth0
	         group 239.0.0.1
	         vni 1
	     }
	 }
	 


ToDo
====
- some configurations under _interfaces vxlan vxlanX_
- some vxlan attributes (e.g, l2miss, l3miss and more)
- push to vyos repo ?


Contact
=======
upa@haeena.net
