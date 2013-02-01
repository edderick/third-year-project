Telnet
======

I think it should be possible to use vtysh to talk to the various daemons. 
I seemed to be able to get it to work by configuring with the flag
--enable-vtysh .


Instead, I have been using telnet:

telnet :: daemon name

e.g. telnet :: zebra
