.. index:: ! Generating_DEM 

**************
Generating_DEM     
**************

Methods and Sources for Generating DEM Files 
--------------------------------------------

Here we list some available methods for generating and downloading
Digital Elevation Model (DEM) files for InSAR processing. 

   * Generating DEM through the GMTSAR topex server
   * Generating DEM through GMT via GMTSAR script :doc:`make_dem.csh`
   

Generating DEM through topex server
-----------------------------------

To download a maximum 4x4º size grid of DEM from SRTM1, SRTM3 or
ASTER-1 visit the website: https://topex.ucsd.edu/gmtsar/demgen/

Enter your chosen latitude and longitude boundaries and your preferred
DEM source and click "Generate".

Once the request is finished you can download the zipped file. 
(Sometimes you need to right-click to download as a file).

   * NOTE: If you area crosses the equator, you may need to download each area above and below the equator separately and then paste them together (check out GMT grdpaste to do so)
   * NOTE: If you need a larger than 4x4deg area, you can always download smaller areas and paste them together with GMT grdpaste

Generating DEM via GMT 
----------------------

This uses the GMTSAR script :doc:`make_dem.csh` which uses the GMT server to
download SRTM 1-arcsecond data (@earth_relief_01s) and removes the EGM96 geoid
to make heights relative to WGS84.

To run, you need to know your region of interest's latitude and longitude
bounds

 ::

   make_dem.csh -122 -115 32 36

This will output a dem.grd, with heights relative to the WGS84 ellipsoid





