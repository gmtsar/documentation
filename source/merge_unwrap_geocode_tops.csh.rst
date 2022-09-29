.. index:: ! merge_unwrap_geocode_tops.csh

*****************************
merge_unwrap_geocode_tops.csh
*****************************

Synopsis
--------
**merge_unwrap_geocode_tops.csh** *inputfile config_file* 

Description
-----------
**merge_unwrap_geocode_tops.csh** merges subswaths together 

This script is called inside :doc:`merge_batch.csh` 

Required Arguments
------------------

*inputfile*

	List of files needed for merging subswaths.

	Inputfiles should be as following:

		Swath1_Path:Swath1_master.PRM:Swath1_repeat.PRM

		Swath2_Path:Swath2_master.PRM:Swath2_repeat.PRM

		Swath3_Path:Swath3_master.PRM:Swath3_repeat.PRM

	(Use the repeat PRM which contains the shift information.)

	e.g. ../F1/intf/2015016_2015030/:S1A20151012_134357_F1.PRM

	Make sure under each path, the processed phasefilt.grd, corr.grd and mask.grd exist.

	Also make sure the dem.grd is linked. 


*config_file* 

	The same batch.config file as used in processing

Example
-------
 ::

    merge_unwrap_geocode_tops.csh filelist batch.config 
