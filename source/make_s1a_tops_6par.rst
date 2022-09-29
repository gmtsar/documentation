.. index:: ! make_s1a_tops_6par

******************
make_s1a_tops_6par
******************

Synopsis
--------
**make_s1a_tops_6par** *xml_file tiff_file output mode rng_shift azi_shift stretch_a a_stretch_a stretch_r a_stretch_r*

Description
-----------
**make_s1a_tops_6par**  

Required Arguments
------------------

*xml_file*     

	Name of xml file 

*tiff_file*    

	Name of tiff file 

*output*       

	Stem name of output files .PRM, .LED, .SLC 

*mode*         

	(0) no SLC; (1) center SLC; (2) high SLCH and low SLCL 

*rng_shift*    

	Fractional part of desired range shift 

*azi_shift*    

	Fractional part of desired azimuth shift 

*stretch_a*    

	Additional azimuth shift in range dir 

*a_stretch_a*  

	Additional azimuth shift in azimuth dir 

*stretch_r*    

	Additional range shift in range dir 

*a_stretch_r*  

	Additional range shift in azimuth dir


Example
-------
 ::

       make_slc_s1a_tops_6par s1a-s1-slc-vv-20140807.xml s1a-s1-slc-vv-20140807.tiff S1A20140807 1 0.4596 .9109 2.18065e-06 -3.63255e-06 1.37343e-05 -3.13352e-05

Output: S1A20140807.PRM S1A20140807.LED S1A20140807.SLC

