.. index:: ! select_pairs.csh

****************
select_pairs.csh
****************

Synopsis
--------
**select_pairs.csh** *baseline_table.dat threshold_time threshold_baseline*

Description
-----------
**select_pairs.csh** generate the input file for intf_tops.csh with given threshold of time and baseline.

This outputs an **intf.in** file, which is the primary input file for :doc:`intf_tops.csh` or :doc:`intf_tops_parallel.csh`

Required Arguments
------------------

*baseline_table.dat*  

	Table of calculated baselines for your images (if missing use :doc:`get_baseline_table.csh` to generate a new one)

*threshold_time*      

	Temporal baseline threshold in days

*threshold_baseline*  

	Spatial perpendicular baseline in meters


Example
-------
 ::

    select_pairs.csh baseline_table.dat 90 150  
