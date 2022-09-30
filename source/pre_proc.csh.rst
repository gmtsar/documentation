.. index:: ! pre_proc.csh   

************
pre_proc.csh  
************

Synopsis
--------
**pre_proc.csh** *SAT master_stem aligned_stem [-near near_range] [-radius RE] [-npatch num_patches] [-fd1 DOPP] [-ESD mode]*

Description
-----------
**pre_proc.csh** 

Required Arguments
------------------

*SAT*

	Satellite

*master_stem*

	Name stem of the master or reference image

*aligned_stem*

	Name stem of the aligned or secondary image

Optional Arguments
------------------

**-near** *near_range*

	Near range value

**-radius** *RE*

	Radius of the Earth

**-npatch** *num_patches*

	Number of patches

**-fd1** *DOPP*

	Doppler

**-ESD** *mode*

	Processing mode for Enhanced Spectral Diversity

Example
-------
 ::

    pre_proc.csh ALOS IMG-HH-ALPSRP099496420-H1.0__A IMG-HH-ALPSRP220276420-H1.0__A
