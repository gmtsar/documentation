.. index:: ! gnss_enu2los.csh

****************
gnss_enu2los.csh
****************

Synopsis
--------
**gnss_enu2los.csh** *master.PRM master.LED gnss.sllenu dem.grd*

Description
-----------
**gnss_enu2los.csh** will convert given east/north/up GNSS observations to Line-Of-Sight (LOS) 

This can be used in three main ways:

(1) Converting a single GPS station time series to LOS (one station for every run)

(2) Converting a set of displacements over a specific time period observed at many GPS station points

(3) Converting a set of estimated GPS velocities 

The output of this script can be directly input into another script called :doc:`correct_insar_with_gnss.csh` which can correct an interferogram (or InSAR velocity field if you have run a time series) with GPS data.


GPS displacement and velocity data can be acquired from many sources. Check out these resources to learn more and find data for your area:

*Scripps Orbit and Permanent Array Center (SOPAC) and NASA MEaSUREs ESESES time series:*

Interactive Map and time series viewer: http://mgviz.ucsd.edu/?mission=ESESES

Download time series: http://sopac-csrc.ucsd.edu/index.php/displacements/



*University of Nevada, Reno, Nevada Geodetic Laboratory (NGL):*

Interactive Map: http://geodesy.unr.edu/NGLStationPages/gpsnetmap/GPSNetMap.html

Home page: http://geodesy.unr.edu/index.php



Required Arguments
------------------

*master.PRM*           

	PRM file for the master SAR image
  
*master.LED*          

	LED file for the master SAR image. Ensure that this is the same .LED file listed in your master.PRM file (they must match)
  
*gnss.llenu*         

	GNSS displacements. Assumes the gnss.llenu file is a list of stations with a specific displacement value (e.g. the displacement between two insar scenes, or the velocity of a single point) per station in millimeters or millimeters/yr.

	Format: StationCode  Longitude  Latitude  East  North  Up 
  
*dem.grd*              

	DEM grid file from your insar processing
 

Example
-------
 ::

   gnss_enu2los.csh  master.PRM master.LED gnss_2019-2018.sllenu dem.grd 
