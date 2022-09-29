.. index:: ! extract_one_time_series.csh

***************************
extract_one_time_series.csh
***************************

Synopsis
--------
**extract_one_time_series.csh** *longitude latitude masterPRM dem.grd scene.tab [m_rng m_azi]*

Description
-----------
**extract_one_time_series.csh** Extracts a LOS time series from existing disp_YYYYDDD.grd files produced by the :doc:`sbas` program

Output: **time_series.dat** will have two colums of data, displacements and standard deviation 

Required Arguments
------------------

*longitude/latitude*     

	Point of interest

*masterPRM*              

	Master PRM file

*dem.grd*                
	
	dem.grd file from processing 

*scene.tab*              

	The same input file needed by :doc:`sbas` . Check out :doc:`prep_sbas.csh` to make a scene.tab file from scratch.
  
 
Optional Arguments
------------------

*m_rng* and *m_azi*       

	The number of pixels to be averaged for output, default is 5 5


Example
-------
 :: 

    extract_one_time_series.csh -119.782 36.292 supermaster.PRM dem.grd scene.tab  
