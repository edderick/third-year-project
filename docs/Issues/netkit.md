Netkit
======

Netkit is a network emulation tool that allows you to very easily run several
debian virtual machines, one one host pc.

__Note__: I should really rave about how good this would be to get the second
years doing; You just can't get this kind of understanding through studying
alone. 

Building Quagga for NetKit
--------------------------

I have created file system image of a file system ready to have quagga made and
installed. This can be done in the same way as it would be done natively under
ubuntu (on the vm itself).

To use this file system, remove the current fs folder and replace it by untaring the new fs it with:

tar -xjSf netkit_quagga_fs.tar.bz2

To make updates to the file system, run a vm as rootin no cow mode:

sudo su
vstart moo --no-cow --eth0=tap,10.0.0.1,10.0.0.2 -M 512

eth0 gives this vm access to the internet. M 512 attempts to prevent it from running out of RAM.

Before creating a new file system image, make sure to stop the instance with:

vhalt -r moo 

Then tar it up with:

tar -cjSf name.tar.bz fs

Labs
----

In NetKit, a lab is a method of creating many VMs set up with interfaces
connected to specified collision domains. 

I don't think that .disk files should be relied on - instead files should be
added to the directory structure to be coppied in on boot, or script files
added for startup and shutdown.

