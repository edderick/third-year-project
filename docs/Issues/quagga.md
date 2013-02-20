Quagga
======
Quagga tends to implement a lot of things from scratch. I'm not sure whether
this is a little bit of "not invented here", if it's the done thing with C
code, or it is just a good way to improve portability and reduce dependence on
a given platform (I believe Quagga supports most variants of *NIX). 

LinkList
--------
Quagga implements it's own Linked List data structure. There are a few
different structs that allow this. Unfortunately, this list implementation
doesn't seem very safe. Since there are no objects, there is no type checking -
elements of the list are simply stored as void pointers. 

There are several methods and macros that act on these lists, the most notable
being ALL_LIST_ELEMENTS.

Threads
-------
There is also a threading system included. I think this is for application
level threads rather than kenel level threads...

IP Adresses
-----------

lib/prefix.h defines some useful stuff. Most notably: IPV6_ADDR_SAME( *addr1,
*addr2) which uses memcmp to check for equality.
