.. index:: ! make_slc_s1a

************
make_slc_s1a
************

Synopsis
--------
**make_slc_s1a** *name_of_xml_file name_of_tiff_file name_output*

Description
-----------
**make_slc_s1a**

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

    make_slc_s1a s1a-s1-slc-vv-20140807.xml s1a-s1-slc-vv-20140807.tiff S1Avv_20140807    

Output: S1Avv_20140807.SLC S1Avv_20140807.PRM S1Avv_20140807.LED
