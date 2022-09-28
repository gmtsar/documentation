.. index:: ! dump_orbit_envi.pl

******************
dump_orbit_envi.pl
******************

Synopsis
--------
**dump_orbit_envi.pl** *start_time stop_time envi.LED orbdir*  

Description
-----------
**dump_orbit_envi.pl**  


Output: envi.LED stores the orbit information, used by ENVI_baseline with format: 

        year day_of_year sec_of_day x y z vx vy vz 


Required Arguments
------------------

*start_time*

	Start time in Julian day format

*stop_time*

	Stop time in Julian day format

*envi.LED*
	
	Relevant ENVISAT LED file

*orbdir*

        orbdir directory with Doris orbit data 


Example
-------
 ::

    dump_orbit_envi.pl 
