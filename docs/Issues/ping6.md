Ping6
=====

The IPV6 ping tool. 

IPV6 addresses cannot be pinged using normal `ping`, instead ping6 must be
used. To use a machines link local IPv6 you must specify the interface that should be used to reach the host.

Examples
--------

* ping6 :: => Pings local host
* ping6 -I eth0 fe80::8e89:a5ff:fe67:b18e 

Note
----

I couldn't work out how to do ping6 localhost.

