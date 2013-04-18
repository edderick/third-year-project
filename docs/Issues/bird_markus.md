Markus Stenberg's Implementation 
================================

Markus' implementation is based on Bird. It is written mostly in lua.  The
code makes use of an extension to Bird called Bird-Ext-LSA - I don't think the
use of the term "External-LSA" here refers to the built in LSA type, rather it
refers to the fact that the code handling the LSA is external to the core of
bird. 

Being very inexperienced in using lua (and in using Bird) I have so far been
unable to run this code. 

OpenWRT Convenience Build 
=========================

There exists a build for OpenWRT. I think that this might be the best way to
get Markus' code up and running.

./configure --enable-ipv6 --with-lua-includes=/usr/include/lua5.1 --with-lua-libraries=/usr/lib/i386-linux-gnu/ --with-lua-suffix=5.1

Problems
========

Uses A different AC_LSA Type. To maintain compatibility with Jari's possibly
private implementation, a different LSA type was used, this can be switched
back by uncommenting a line of code. 

Is also implemented incorrectly. The length field should be for the value part
of the tlv, not the whole thing.

Once that issue is fixed, it turns out that Assigned prefixes relied on this
brokenness to work at all. The if id is a weird header entry. Need to modify
this to allow interop.
