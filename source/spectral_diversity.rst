.. index:: ! spectral_diversity   

******************
spectral_diversity
****************** 

Synopsis
--------
**spectral_diversity** *master_stem aligned_stem bshfit filter*


Description
-----------
**spectral_diversity**  

Output: resitual_shift = 0.001234  [with a file ddphase]

Note: make sure stem.SLCH stem.SLCL stem.BB exist              

Required Arguments
------------------

*master_stem*

	Name stem of master or reference image

*aligned_stem*

	Name stem of aligned or secondary image

*bshfit*

	Input

*filter*

	Input filter name


Example
-------
 ::

    spectral_diversity S1A20150322_F1 S1A20150415_F1 0 gauss5x5



