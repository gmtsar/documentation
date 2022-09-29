.. index:: ! make_a_offset.csh

*****************
make_a_offset.csh
*****************

Synopsis
--------
**make_a_offset.csh** *Master.PRM Aligned.PRM nx ny xsearch ysearch do_xcorr*

Description
-----------
**make_a_offset.csh**

Required Arguments
------------------

*nx*  

	Number of offsets to compute in the range direction (~num_rng/4)  

*ny*  

	Number of offsets to compute in the azimuth direction (~num_az/6)  

*xsearch*  

	Size of correlation window in range (e.g., 16) 

*ysearch*  

	Size of correlation window in azimuth (e.g., 16) 

*do_xcorr*  

	1-recalculate xcorr; 0-use results from previous xcorr 

Example
-------
 ::

    make_a_offset.csh 
