X-Compiling
===========

Since Alix2d3s are very slow, a build of Quagga can be very slow. The make parts
alone can take around 15 minutes. (I actually found that XORP had an even slower
compile time) 

To over come this issue it is possible to compile the source code on a much
faster machine (e.g. desktop pc) and copy it across. 

Since modern machines use a 64bit architecture rather than 32bit like the
Alix2d3s, the compiler must be set up correctly. Adding the cflag "-m32" should
suffice, however to be on the safe side, "-m32 -march=i386" can be used. 

I initially had problems with this compilation. I resolved the issues by going
back to basics and trying to compile a simple helloworld program for the Alix.
Turns out I was missing "gcc-multilib". This can be installed with apt.
