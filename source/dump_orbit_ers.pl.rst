.. index:: ! dump_orbit_ers.pl

*****************
dump_orbit_ers.pl
*****************

Synopsis
--------
**dump_orbit_ers.pl** *orbit_frame orbdir*  

Description
-----------
**dump_orbit_ers.pl**


Output: orbit_frame.LED store the orbit information, used by ERS_baseline with format: 

        year day_of_year sec_of_day x y z vx vy vz  

Required Arguments
------------------

*orbit_frame*

	orbit_frame.PRM file

*orbdir*

        orbdir directory with PRC orbit data 


Example
-------
 ::

    dump_orbit_ers.pl  
