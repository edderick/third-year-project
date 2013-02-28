Zebra
=====

Quagga provides a daemon, called zebra, that abstracts away interacting with
the underlying operating system. Functions such as altering the routing table
and setting IPv6 Addresses can be performed by this daemon. 

Almost all (All?) of the functionality is provided to the end-use through the
vty (over telnet). Some of the functionality is also available through a
protocol exposed to the other routing daemons. 

This protocol can be used by calling the function:

> zebra_send_message (struct zclient* zclient);

__NOTE: Not message_send!!__

This function sends a message to zebra based on the state of zclient->obuf.
obuf (The output buffer) is a stream - another in house data structure. The
message itself can be set using stream-putw and stream-putc.

Calls to this function should ideally not be made from the routing daemons
themselves, but rather, encapsulated in the library.

I shall be duct taping on some functionality to the side of this protocol. 
