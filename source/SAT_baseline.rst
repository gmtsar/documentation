.. index:: ! SAT_baseline 

************
SAT_baseline 
************

Synopsis
--------

**SAT_baseline** *PRM_master* *inputfile* 


Description
-----------
**SAT_baseline**  

Mode 1: **SAT_baseline** PRM_master PRM_master        

This is used to compute height information (writes out height information for appending to PRM file)


Mode 2: **SAT_baseline** PRM_master PRM_aligned

Please make sure the orbit file data is in PRM 
Program runs through repeat orbit to find nearest point 
to the start, center and end on the reference orbit
(writes out parameters for appending to PRM file)

Required Arguments
------------------

Mode 1:

*PRM_master*

	Parameter file for the master or reference image

*PRM_master*

	Parameter file for the master or reference image

Mode 2:

*PRM_master*

	Parameter file for master or reference image

*PRM_aligned*

	Parameter file for aligned or secondary image


Example
-------
 ::

    SAT_baseline master.PRM master.PRM          


