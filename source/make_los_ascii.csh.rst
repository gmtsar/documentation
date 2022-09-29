.. index:: ! make_los_ascii.csh

******************
make_los_ascii.csh
******************

Synopsis
--------
**make_los_ascii.csh** *los.grd dem.grd -I0.01/0.01 PRM_file Satellite*

Description
-----------
**make_los_ascii.csh** 

Required Arguments
------------------

*los.grd*

	Grid file in LOS

*dem.grd*

	DEM file used for processing

*-I0.01/0.01*

	Increment 

*PRM_file*

	Relevant parameter (PRM) file

*Satellite*

	Specify what Satellite

Example
-------
 ::

    make_los_ascii.csh los_ll.grd dem.grd -I0.01/0.01 IMG-HH-ALOS2046743050-150405-WBDR1.1__D-F1.PRM ALOS 
