Installing Quagga
=================

This is a procedure that has  turned out to be far more difficult that anticipated. 

First of all, need to ensure that all the dependencies are present. The easiest
way I have found to do this is to use:

sudo apt-get build-dep quagga

This should fetch all the packages that quagga depends on. I see no reason to
build these from source, since I shall not be modifying them. 

Next it should be possible to run ./bootstrap. AFAIK this produces (among other
things) the configure script. 

Next run the configure script. This [wiki][wiki] suggests that it is best to
move the folders using:

sudo ./configure --sysconfdir=/usr/local/quagga --localstatedir=/usr/local/quagga

The configure script will prompt you to create a user called quagga. Do this by:

sudo adduser quagga
sudo mkdir /usr/local/quagga
sudo chown quagga:quagga /usr/local/quagga

It is now time to run make. See the crosscompiling document for more
information about this. Previously I had issues with zebra making, to fix this
manually editing the Makefile in ./zebra by adding -lcap to LIBS. This doesn't
seem to be a problem with the latest source.

Run sudo make install. This should install everything, and the daemons
should have installed themselves to /usr/local/sbin. 

Now a little bit of configuration is required. cd /usr/local/quagga. 
Either make a real config file for the daemon, or just create a file containing "password test".


You should now be able to run sudo ospf6d.


[wiki]: http://wiki.nil.com/Installing_and_running_Quagga
