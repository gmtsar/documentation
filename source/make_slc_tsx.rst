.. index:: ! make_slc_tsx

************
make_slc_tsx
************

Synopsis
--------
**make_slc_tsx** *name_of_xml_file name_of_image_file name_output*

Description
-----------
**make_slc_tsx** converts TerraSAR-X date to GMTSAR-readable input file format

Required Arguments
------------------

*name_of_xml_file*

	Name of input .xml file

*name_of_image_file*

	Name of input image file

*name_output*

	Name stem of output .SLC, .PRM, and .LED files 

Example
-------
 ::

    make_slc_tsx TSX1_SAR__SSC______SM_S_SRA_20120615T162057_20120615T162105.xml IMAGE_HH_SRA_strip_007.cos TSX_HH_20120615

Output: TSX_HH_20120615.SLC TSX_HH_20120615.PRM TSX_HH_20120615.LED
