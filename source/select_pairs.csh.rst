.. index:: ! select_pairs.csh

**************
select_pairs.csh
**************

Synopsis
--------
**select_pairs.csh** *baseline_table.dat threshold_time threshold_baseline*

Description
-----------
**select_pairs.csh** generate the input file for intf_tops.csh with given threshold of time and baseline.

Input:

  baseline_table.dat -- table of calculated baselines for your images (if missing use :doc:`get_baseline_table.csh` to generate a new one)

  threshold_time     -- temporal baseline threshold in days

  threshold_baseline -- spatial perpendicular baseline in meters

Output:

  intf.in            -- primary input file for `intf_tops.csh` or `intf_tops_parallel.csh`

Example
-------
  **select_pairs.csh** baseline_table.dat 90 150  
