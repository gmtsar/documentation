.. index:: ! assemble_tops        

*************      
assemble_tops     
*************      

Synopsis
--------
**assemble_tops**  *azi_1 azi_2 name_stem1 name_stem2 ... output_stem* 


Description
-----------
**assemble_tops** stitches TOPS mode data together to make a larger frame
    

Note: output files are bursts that covers area between azi_1 and azi_2, set them to 0s to output all bursts

Required Arguments
------------------

*azi_1*

	Azimuth 1

*azi_2* 

	Azimuth 2

*name_stem1*

	Name stem of first frame data file

*name_stem2*

	Name stem of second frame data file

*output_stem*

	Name stem of final output stitched frame

Example
-------
 ::

    assemble_tops 1685 9732 s1a-iw1-slc-vv-20150706t135900-20150706t135925-006691-008f28-001 s1a-iw1-slc-vv-20150706t135925-20150706t135950-006691-008f28-001 s1a-iw1-slc-vv-20150706t135900-20150706t135950-006691-008f28-001

Expected output: s1a-iw1-slc-vv-20150706t135900-20150706t135950-006691-008f28-001.xml s1a-iw1-slc-vv-20150706t135900-20150706t135950-006691-008f28-001.tiff 


