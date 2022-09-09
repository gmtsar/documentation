.. index:: ! make_a_offset.csh

**************
make_a_offset.csh
**************

Synopsis
--------
**make_a_offset.csh** *Master.PRM Aligned.PRM nx ny xsearch ysearch do_xcorr*

Description
-----------
**make_a_offset.csh**

       nx - number of offsets to compute in the range direction (~num_rng/4)  
       ny - number of offsets to compute in the azimuth direction (~num_az/6)  
       xsearch - size of correlation window in range (e.g., 16) 
       ysearch - size of correlation window in azimuth (e.g., 16) 
       do_xcorr - 1-recalculate xcorr; 0-use results from previous xcorr 

Example
-------
  **make_a_offset.csh** 
