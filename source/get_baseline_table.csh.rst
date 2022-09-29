.. index:: ! get_baseline_table.csh

**********************
get_baseline_table.csh
**********************

Synopsis
--------
**get_baseline_table.csh** *prmlist master_prm* 

Description
-----------
**get_baseline_table.csh** Produce a time series baseline_table.dat file from a batch list of .PRM files 

Required Arguments
------------------

*prmlist*

	List of PRM files in your time series

*master_prm*

	The chosen master or reference image PRM file

Example
-------
 ::

   get_baseline_table.csh PRM.list supermaster.PRM 
