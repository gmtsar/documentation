.. index:: ! intf_batch_ALOS2_SCAN.csh

*************************      
intf_batch_ALOS2_SCAN.csh
*************************      

Synopsis
--------
**intf_batch_ALOS2_SCAN.csh** *SAT intf.in batch.config*


Description
-----------
**intf_batch_ALOS2_SCAN.csh** make a stack of ALOS2 ScanSAR interferograms listed in intf.in

Required Arguments
------------------

*SAT*

	SAT can only be ALOS2  

*intf.in*

	List of image pairs to calculate interferograms for
	
	format for intf.in:

		reference1_name:repeat1_name

		reference2_name:repeat2_name

		reference3_name:repeat3_name

		etc.



	*Example of intf.in for ALOS2 ScanSAR*

		IMG-HH-ALOS2101532950-160409-WBDR1.1__D:IMG-HH-ALOS2149142950-170225-WBDR1.1__D

		IMG-HH-ALOS2101532950-160409-WBDR1.1__D:IMG-HH-ALOS2155352950-170408-WBDR1.1__D


*batch.config*

	Configuration file for making interferogram. It can be created using :doc:`pop_config.csh`  for ALOS2 files


Example
-------
 ::

    intf_batch_ALOS2_SCAN.csh ALOS2 intf.in batch.config


