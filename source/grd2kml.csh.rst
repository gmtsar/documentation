.. index:: ! grd2kml.csh

*******
grd2kml.csh
*******

Synopsis
--------
**grd2kml.csh** *grd_file_stem cptfile [-R<west>/<east>/<south>/<north>]*

Description
-----------
**grd2kml.csh** converts a given grid (.grd) file into a Google Earth KML file using a user-specified color palette.

Input:

    grd_file_stem  -  the name (without file extension) of your grd file (must be in geocoded (lat/lon) coordinates)

    cptfile        -  color palette file (can be created using `gmt makecpt`, see usage)

Output:
 
    grd_file_stem.png  - PNG file of grid information
   
    grd_file_stem.kml  - Google Earth file; this file and the above png file must be stored together to be read in by Google Earth

Example
-------
    **grd2kml.csh** phase phase.cpt   
