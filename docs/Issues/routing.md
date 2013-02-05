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
/proc/sys/net/ipv4/ip_forward to 1. This isn't a persistant change, but does
take effect immediately. 

For a more permenent solution, use google, then update this document after
testing :) Thanks.

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

Will do what you want on a linux machine. 

For the Thomson "O2 Wireless Box", you can telnet into it and then use the ip
section followed by the various rt commands to configure a static route.

