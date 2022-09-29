.. index:: ! grd2kml.csh

***********
grd2kml.csh
***********

Synopsis
--------
**grd2kml.csh** *grd_file_stem cptfile [-R<west>/<east>/<south>/<north>]*

Description
-----------
**grd2kml.csh** converts a given grid (.grd) file into a Google Earth KML file using a user-specified color palette.

This outputs a PNG file which contains the grid information, and a .KML file which is the Google Earth display file. These output files both are named with the user-specified file_stem, and they must be stored together in the same directory in order to display properly in Googe Earth.
 

Required Arguments
------------------

*grd_file_stem*     

	The name (without file extension) of your grd file (must be in geocoded (lat/lon) coordinates)

*cptfile*           

	Color palette file (can be created using GMT tool makecpt, see usage here: https://docs.generic-mapping-tools.org/dev/makecpt.html )

Optional Argument
-----------------

*-R<west>/<east>/<south>/<north>*

	Range if you wish to output only a subarea of your grid file
 
Example
-------
 ::

    grd2kml.csh phase phase.cpt   
