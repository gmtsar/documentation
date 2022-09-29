.. index:: ! m2s.csh

*******
m2s.csh
*******

Synopsis
--------
**m2s.csh** *pixel_size_in_meters llpfile*

Description
-----------
**m2s.csh** Convert pixel dimension in meters to dx/dy in arc seconds at mean latitude 

Required Arguments
------------------

*pixel_size_in_meters*    

	Input pixel dimension in meters

*llpfile*   

	Longitude, latitude, phase binary float file


Example
-------
 ::

    m2s.csh 150 input.llp 
