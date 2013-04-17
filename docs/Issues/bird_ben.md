Ben Paterson's Implementation
=============================

Ben's implementation is based on BIRD. It is a fork of BIRD that adds
(potentially among other things) the features specified in the drafts.

Unlike Markus' code, it is written entirely in C and as such I found it much
easier to compile. 

Interop Testing
===============

Brief testing indicates that my implementation is compatible (for the bits that
I have already implemented). I found that testing by replacing one of the
Quagga netkit instances works well.

Problems
========

This implentation seems to work well for the first draft, but doesn't seem to implement the second draft at all correctly. It instead uses a completely different scheme for its assigned prefix tlvs, introducing a fourth tlv type to idenity the interface,
