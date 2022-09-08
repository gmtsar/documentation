.. index:: ! SAT_baseline 

************
SAT_baseline 
************

Synopsis
--------

**SAT_baseline** *PRM_master* *PRM_master* 


Description
-----------
**SAT_baseline** PRM_master inputfile 

Mode 1: **SAT_baseline** PRM_master PRM_master        


This is used to compute height information
(writes out height information for appending to PRM file)


Mode 2: **SAT_baseline** PRM_master PRM_aligned

PRM_master 	   PRM file for reference image
PRM_aligned 	   PRM file of secondary image
Please make sure the orbit file data is in PRM 
Program runs through repeat orbit to find nearest point 
to the start, center and end on the reference orbit
(writes out parameters for appending to PRM file)


Example
-------
    **SAT_baseline** master.PRM master.PRM          


