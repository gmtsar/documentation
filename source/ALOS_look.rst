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

 master.PRM   -  parameter file for master image and points to LED orbit file 
 inputfile    -  lon, lat, elevation [ASCII] 
 outputfile   -  lon, lat, elevation look_E look_N look_U [ASCII default] 
 -bos or -bod   -  binary single or double precision output


Example
-------
    **ALOS_look** master.PRM < topo.llt > topo.lltn 


