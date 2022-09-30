.. index:: ! pre_proc_batch.csh

******************
pre_proc_batch.csh
******************

Synopsis
--------
**pre_proc_batch.csh** *SAT data.in batch.config* 

Description
-----------
**pre_proc_batch.csh** Preprocess a set of images using a common rear_range and radius 

Required Arguments
------------------

*SAT*

	SAT can be ALOS ERS ENVI(ENVISAT) ENVI_SLC

*data.in*

	List of input data to be aligned in a batch process. Ensure that the first line listed in the data.in file is your chosen master or reference image.

	Format of data.in is:
 
		line 1: master_name 
 
		line 2 and onward: aligned_name


	*example of data.in for ALOS is:*
 
		IMG-HH-ALPSRP096010650-H1.0__A
 
		IMG-HH-ALPSRP089300650-H1.0__A
 
		IMG-HH-ALPSRP236920650-H1.0__A


	*example of data.in for ERS is:*
  
		e1_05783
 
		e1_07787
 
		e1_10292


	*example of data.in for ENVISAT is:*
 
		ENV1_2_127_2925_07195
 
		ENV1_2_127_2925_12706
 
		ENV1_2_127_2925_13207


	*example of data.in for ENVI_SLC is:*
 
		ASA_IMS_1PNESA20030908_175832_000000182019_00399_07968_0000
 
		ASA_IMS_1PNESA20040719_175832_000000182028_00399_12477_0000
 
		ASA_IMS_1PNESA20051121_175837_000000172042_00399_19491_0000

*batch.config*

	Configuration file. If you need to create a default config file, use :doc:`pop_config.csh`

Example
-------
 ::

    pre_proc_batch.csh ENVI data.in batch.config 
