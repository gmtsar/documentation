.. index:: ! make_slc_csk

************
make_slc_csk
************

Synopsis
--------
**make_slc_csk** *name_of_input_file name_output*

Description
-----------
**make_slc_csk** converts Cosmo SkyMed data into GMTSAR-readable input files

Required Arguments
------------------

*name_of_input_file*

	Name of file to be operated on

*name_output*

	Name step of output .SLC, .PRM, and .LED files 

Example
-------
 ::

    make_slc_csk RCSKS2_SCS_B_HI_09_HH_RA_SF_20090412050638_20090412050645.h5 CSK_20090412

Output: CSK_20090412.SLC CSK_20090412.PRM CSK_20090412.LED
