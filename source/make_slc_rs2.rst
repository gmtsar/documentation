.. index:: ! make_slc_rs2

************
make_slc_rs2
************

Synopsis
--------
**make_slc_rs2** *name_of_xml_file name_of_tiff_file name_output*

Description
-----------
**make_slc_rs2** converts Radarsat2 data into GMTSAR-readable input data

Required Arguments
------------------

*name_of_xml_file*

	Name of input .xml file

*name_of_tiff_file*

	Name of input .tiff file

*name_output*

	Name stem of output .SLC, .PRM and .LED files 

Example
-------
 ::

    make_slc_rs2 product.xml imagery_HH.tif RS220110515 

Output: RS220110515.SLC RS220110515.PRM RS220110515.LED   
