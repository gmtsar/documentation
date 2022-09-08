.. index:: ! assemble_tops        

************      
assemble_tops     
************      

Synopsis
--------
**assemble_tops**  *azi_1 azi_2 name_stem1 name_stem2 ... output_stem* 


Description
-----------
**assemble_tops** stitches TOPS mode data together to make a larger frame
    

Note: output files are bursts that covers area between azi_1 and azi_2, set them to 0s to output all bursts

Example
-------
    **assemble_tops** 1685 9732 s1a-iw1-slc-vv-20150706t135900-20150706t135925-006691-008f28-001 s1a-iw1-slc-vv-20150706t135925-20150706t135950-006691-008f28-001 s1a-iw1-slc-vv-20150706t135900-20150706t135950-006691-008f28-001

Expected output: s1a-iw1-slc-vv-20150706t135900-20150706t135950-006691-008f28-001.xml s1a-iw1-slc-vv-20150706t135900-20150706t135950-006691-008f28-001.tiff 


