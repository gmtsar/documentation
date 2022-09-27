.. index:: ! cleanup.csh       

******************
cleanup.csh
******************

Synopsis
--------
**cleanup.csh** *directory*  


Description
-----------
**cleanup.csh** Clean the disk area 

Required Argument

*directory*

    directory could be: raw, SLC, topo, intf, or all

*WARNING: This will remove intermediate processing files that take time to replicate. Clean cautiously and wisely.*


Example
-------
 ::

    cleanup.csh all 


