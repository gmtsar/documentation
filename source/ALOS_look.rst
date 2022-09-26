.. index:: ! ALOS_look    

************
ALOS_look    
************

Synopsis
--------
**ALOS_look** *master.PRM* *[-bo[s|d]]* < *inputfile* > *outputfile*


Description
-----------
**ALOS_look** calculates the look direction of given point or points from an input file        

ALOS_look reads in an input file of longitude, latitude, and elevation and outputs
a file of longitude, latitude, elevation, look_E, look_N, and look_U 
(ASCII file default)

Required Arguments
------------------

*master.PRM*  

	Parameter file for master image and points to LED orbit file 

*inputfile*  

	Format: Longitude, Latitude, Elevation(m) [ASCII] 

*outputfile*   

	Format: Longitude, Latitude, Elevation(m), look_East, look_North, look_Up [ASCII default] 

*-bos*  or  *-bod*   

	Binary single (s) or double (d) precision output


Example
-------
 ::

    ALOS_look master.PRM < topo.llt > topo.lltn 


