.. index:: ! grd2geotiff.csh

***************
grd2geotiff.csh
***************

Synopsis
--------
**grd2geotiff.csh** *grd_file_stem cptfile [-R<west>/<east>/<south>/<north>]*

Description
-----------
**grd2geotiff.csh** converts a grid (.grd) file to a geotiff file 

Required Arguments
------------------

*grd_file_stem*

	Name stem of the grid file to be operated on

*cptfile*

	Name of color palette file your wish to use (to make a color palette file in GMT format check out GMT makecpt tool at https://docs.generic-mapping-tools.org/dev/makecpt.html )

Optional Arguments
------------------

*-R<west>/<east>/<south>/<north>*

	Provide a range if you wish to only output a subarea of your grid file

Example
-------
 ::

    grd2geotiff.csh phase phase.cpt
