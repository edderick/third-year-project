Time
====

I found that one of my Alix2d3s decided that it didn't want to have a sensible
system time. This lead to some weird errors, and actually made it impossible to
build quagga. 

To set the time to a correct value I found the best way is probably to use ntp. 

sudo ntpdate ntp.ubuntu.com 

seemed to do the trick. A quick check can be done using date.
