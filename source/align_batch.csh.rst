.. index:: ! align_batch.csh      

***************      
align_batch.csh   
***************      

Synopsis
--------
**align_batch.csh** *SAT align.in*                                          


Description
-----------
**align_batch.csh** align a set of images listed in align.in file 


Required Arguments
------------------

*SAT*

	SAT can be ALOS ENVISAT or ERS

*align.in*

	List of input files to be aligned

	format of align.in:

 		master_name:aligned_name:supermaster_name

	*example of align.in for ALOS is:*

 		IMG-HH-ALPSRP096010650-H1.0__A:IMG-HH-ALPSRP089300650-H1.0__A:IMG-HH-ALPSRP096010650-H1.0__A

		IMG-HH-ALPSRP096010650-H1.0__A:IMG-HH-ALPSRP236920650-H1.0__A:IMG-HH-ALPSRP096010650-H1.0__A
  
	*example of align.in for ERS is:*

		e1_05783:e1_07787:e1_05783

 		e1_05783:e1_10292:e1_05783

	*example of align.in for ENVISAT is:*

		ENV1_2_127_2925_07195:ENV1_2_127_2925_12706:ENV1_2_127_2925_07195

		ENV1_2_127_2925_07195:ENV1_2_127_2925_13207:ENV1_2_127_2925_07195

Example
-------
 ::

    align_batch.csh ALOS align.in                       


