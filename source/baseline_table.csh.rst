.. index:: ! baseline_table.csh

******************
baseline_table.csh
******************

Synopsis
--------
**baseline_table.csh** *master.PRM aligned.PRM [GMT]*  


Description
-----------
**baseline_table.csh** creats a baseline_table.dat file

Input:

    master.PRM  -  PRM file for the master image
 
    aligned.PRM -  PRM file for the secondary/aligned image

    [GMT]       -  creates table for pstext         

Output File format:

sat_orb aligned_time aligned_days(1992ERS,2006ALOS) Bpl Bperp xshift yshift


Example
-------
    **baseline_table.csh** master.PRM aligned.PRM 


