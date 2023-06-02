.. index:: ! Projecting_To_LatLon 

********************
Projecting_To_LatLon 
********************

We often want to project our InSAR results from radar coordinates (range/azimuth) into 
geocoded coordinates in order to view and interpret them. This page walks you through how
to use :doc:`proj_ra2ll.csh` and its inverse :doc:`proj_ll2ra.csh`. 

Projecting Into Geocoded Coordinates
------------------------------------

If you have a grid file in radar coordinates (e.g., a wrapped interferogram, phasefilt.grd or an
unwrapped interferogram, unwrap.grd) and you want to project it to longitude/latitude, you can use
:doc:`proj_ra2ll.csh`. You will need to have the trans.dat file in the same directory (the file that 
contains the transformations between the radar coordinates and geocoded coordinates), as well as a filter
file called "gauss_XXX". A good choice is at least a gauss_600 file.

 ::
 
    proj_ra2ll.csh trans.dat unwrap.grd unwrap_ll.grd

This will project the unwrap.grd grid from radar coordinates to geocoded coordinates. :doc:`proj_ra2ll.csh`
will create two grids raln.grd and ralt.grd that will be used again if you project anything else (they will 
not be overwritten if they exist in the directory).

Converting to GoogleEarth KML file
----------------------------------

GoogleEarth is a great way to view results quickly, you just need to make a KML file:

 ::

    # first make a color palette to plot with
    gmt grd2cpt unwrap_ll.grd -Croma > unwrap_ll.cpt # -C specifies GMT-based color palette, this chooses "roma"
    
    # then make the kml file
    grd2kml.csh unwrap_ll unwrap_ll.cpt 

This will produce a kml file and a png file. These two files need to be in the same directory to open in GoogleEarth. 


Projecting to Radar Coordinates
-------------------------------

Conversely, if you want to project something into radar coordinates, you can use :doc:`proj_ll2ra.csh`.

