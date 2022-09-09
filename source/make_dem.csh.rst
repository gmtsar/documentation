.. index:: ! make_dem.csh

*******
make_dem.csh
*******

Synopsis
--------
**make_dem.csh** *lonW lonE latS latN DEM_type*

Description
-----------
**make_dem.csh** creates a DEM (dem.grd) file using the input lon/lat coordinate boundaries               

  DEM_type: 1--SRTM1 2--SRTM3 3--ASTER

       notes: 1  has not been tested if the tiles cross equator or E180

              2  custom dem.grd also available from http://topex.ucsd.edu/gmtsar

Example
-------
    **make_dem.csh** -125.5 -122.5 30.5 33.5 2  
