.. index:: ! samp_slc.csh   

************
samp_slc.csh  
************

Synopsis
--------
**samp_slc.csh** *image_stem new_prf new_rng_samp_rate*

Description
-----------
**samp_slc.csh** 

Note: A very small change in prf or rng_samp_rate change will be ignored as they can be accounted during normal processing with resamp. Put 0 in new_prf or new_rng_samp_rate to ignore resamping.

Required Arguments
------------------

*image_stem*

	Name stem of image

*new_prf*

	New PRF number to be implemented

*new_rng_samp_rate*

	New range sampling rate to be implemented

Example
-------
 ::

    samp_slc.csh IMG-ALPSRP022200660-H1.1__A 2000 3200000
