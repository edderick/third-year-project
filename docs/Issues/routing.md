Routing
=======

Yup - my whole project is on it, but I don't really know how it works. What a
great opportunity for learning!

I found getting my Alix2d3s set up as routers, using only static routes, was
hard enough! 

Forwarding
----------

Turns out you must explicitly specify that you wish packets to be forwarded by
the router. This can be done at runtime by setting
/proc/sys/net/ipv4/ip_forward to 1. This isn't a persistent change, but does
take effect immediately. 

Note that this is IPv4 only, so is fairly irrelevant for OSPFv3.
/proc/sys/net/ipv6/all/forwarding must be set for IPv6 traffic to be forwarded.

A more permanent solution can be achieved by adding the appropriate lines to
/etc/sysctl.conf

NAT
---

This is something I shouldn't ever have to touch, but to help log things I have
learned, here it is:

sudo iptables --table nat --append POSTROUTING --out-interface eth0 -j MASQUERADE
 
This is the magic command that makes it NAT. This snippit will convert the IP
to the destination subnet. Annothe useful command clears the table:

sudo iptables --table nat --flush

Caveat
------

**If you wish to ping a device, Please make sure that the source is reachable
from the destination!**

The simplest way I have found is to set up a static route, something based on:

sudo route add -net 192.168.3.0/24 gw 192.168.1.111

Note: This is actually a deprecated way of setting this up. iproute2 has
replaced route, use:

sudo ip route add 192.168.3.0/24 via 192.168.1.111

Will do what you want on a Linux machine. 

For the Thomson "O2 Wireless Box", you can telnet into it and then use the ip
section followed by the various rt commands to configure a static route.

Just One Interface
------------------

I had a lot of problems getting this all working. I thought that going in one
interface, and coming back out the same one as a different subnet, should work.
Early experimentation suggested that it didn't. Once all the other kinks were
ironed out, it seemed to work just fine. :)

Adding an IP Address
--------------------

This lil' snippet is pretty useful: 

ip addr add 192.168.3.1/24 broadcast 192.168.3.255 dev eth0 

similarly:

ip addr del 192.168.3.1/24 dev eth0 

and:

ip link set eth2 up
