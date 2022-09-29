.. index:: ! make_s1a_tops

*************
make_s1a_tops
*************

Synopsis
--------
**make_s1a_tops** *xml_file tiff_file output mode dr.grd da.grd*

Description
-----------
**make_s1a_tops**  

Required Arguments
------------------

*xml_file*      

	Name of xml file 

*tiff_file*     

	Name of tiff file 

*output*        

	Stem name of output files .PRM, .LED, .SLC 

*mode*          

	(0) no SLC; (1) center SLC; (2) high SLCH and low SLCL 

*dr.grd*        

	Range shift table to be read in 

*da.grd*        

	Azimuth shift table to be read in 


Note: if dr and da are not given, SLCs will be written with no shifts.

      s1a-aux.xml and manifest.safe(exclude the first line) should be concatenated to the xml_file for 

      acquisitions acquired before Mar 2015 (IPF version change). If not concatenated or IPF version is 2.43+, 

      elevation antenna pattern correction(EAP) will not be applied


Example
-------
 ::

       make_slc_s1a_tops s1a-s1-slc-vv-20140807.xml s1a-s1-slc-vv-20140807.tiff S1A20140807 1 dr.grd da.grd

       make_slc_s1a_tops s1a-s1-slc-vv-20140807.xml s1a-s1-slc-vv-20140807.tiff S1A20140807 1


Output: mode 1: S1A20140807.PRM S1A20140807.LED S1A20140807.SLC

        mode 2: S1A20140807.PRM S1A20140807.LED S1A20140807.SLCH S1A20140807.SLCL S1A20140807.BB
