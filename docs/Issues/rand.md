Pseudorandom Numbers 
====================

For generating random numbers, the GNU standard library provides several
methods. The functions seem to return different values even if seeded with the
same number. 

srand & rand 
============

srand is used to set the seed and rand is used to return and random number. All
state is stored somewhere mystical within C.

rand_r
======

This function is called with a pointer to a seed on each call. This allows the
state to be stored within the seed. Note this function therefore has side
effects.
