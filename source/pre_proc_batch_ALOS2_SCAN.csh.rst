.. index:: ! pre_proc_batch_ALOS2_SCAN.csh

*****************************
pre_proc_batch_ALOS2_SCAN.csh
*****************************

Synopsis
--------
**pre_proc_batch_ALOS2_SCAN.csh** *data.in batch.config* 

Description
-----------
**pre_proc_batch_ALOS2_SCAN.csh** Preprocess a set of ALOS2 SCANSAR images using a common radius and preprocess all 5 subswaths 

Required Arguments
------------------

*data.in*

	List of input data for alignment. Ensure that the first line in your data.in file is your master image.

	Format of data.in is:
 
		line 1: master_name 
 
		line 2 and onward: aligned_name


	*example of data.in for ALOS2 SCANSAR is:*

		IMG-HH-ALOS2047473650-150410-WBDR1.1__D

		IMG-HH-ALOS2101293650-160408-WBDR1.1__D

*batch.config*

	Configuration file. If you need to create a default config file, use :doc:`pop_config.csh`

Example
-------
 ::

    pre_proc_batch_ALOS2_SCAN.csh data.in batch.config 
