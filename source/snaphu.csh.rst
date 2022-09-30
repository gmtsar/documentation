.. index:: ! snaphu.csh     

**********
snaphu.csh    
**********

Synopsis
--------
**snaphu.csh** *correlation_threshold maximum_discontinuity [<rng0>/<rngf>/<azi0>/<azif>]*

Description
-----------
**snaphu.csh** Unwrap the phase

Required Arguments
------------------

*correlation_threshold*    

	Correlation is set to zero is less than the set threshold (if unsure what threshold to start with, try creating a coherence mask first to check)

*maximum_discontinuity*    

	Enables phase jumps for earthquake ruptures, etc. Set to 0 for continuous phase such as interseismic or up to 60 for an event such as an earthquake rupture


Optional Arguments
------------------

*optional range*        

	If you wish to only process a subarea of your input, specify minrange/maxrange/minazimuth/maxazimuth


Example
-------
 ::

    snaphu.csh .12 40 1000/3000/24000/27000


References
----------

Chen C. W. and H. A. Zebker, Network approaches to two-dimensional phase unwrapping: intractability and two new algorithms, Journal of the Optical Society of America A, vol. 17, pp. 401-414 (2000).
