.. index:: ! make_dem.csh

************
make_dem.csh
************

Synopsis
--------
**make_dem.csh** *lonW lonE latS latN DEM_type*

Description
-----------
**make_dem.csh** creates a DEM (dem.grd) file using the input lon/lat coordinate boundaries               

Custom dem.grd also available from http://topex.ucsd.edu/gmtsar

Required Arguments
------------------

*lonW lonE latS latN*

	Range extension of your desired DEM (if your area crosses the equator or E 180 degrees, you may need to pull two grids of dem and paste them together with GMT grdpaste https://docs.generic-mapping-tools.org/6.2/grdpaste.html )

*DEM_type* 

	Choose the source of your DEM data. 
	
	1--SRTM1 2--SRTM3 3--ASTER



Example
-------
 ::

    make_dem.csh -125.5 -122.5 30.5 33.5 2  
