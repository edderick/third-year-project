Local DNS
=========

I was initially unable to connect to various devices on my network by their
hostnames alone: Some devices required hostname.local, others just didn't
work. 

I found that one way of fixing this issue is to run dhclient. Unfortunately,
this prevents static IP addreessing.

It is possible to add an alias address in the dhclient.conf file found in 
/etc/dhcp or /etc/dhcp3.

Specify DNS Server Under Linux
==============================

There **IS** a better way (when I learn it, I should update this), but for now just edit:

/etc/resolv.conf

Job done!
