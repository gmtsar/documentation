.. index:: ! align_batch_ALOS2_SCAN.csh

**************************
align_batch_ALOS2_SCAN.csh
**************************

Synopsis
--------
**align_batch_ALOS2_SCAN.csh** *align.in*                 


Description
-----------
**align_batch_ALOS2_SCAN.csh**  align a set of images listed in align.in file

Required Arguments
------------------

*align.in*

	List of input files to be aligned

	format of align.in:

    		master_name:aligned_name:supermaster_name

  	example of align.in for ALOS2 is:

		IMG-HH-ALPSRP096010650-H1.0__A:IMG-HH-ALPSRP089300650-H1.0__A:IMG-HH-ALPSRP096010650-H1.0__A

		IMG-HH-ALPSRP096010650-H1.0__A:IMG-HH-ALPSRP236920650-H1.0__A:IMG-HH-ALPSRP096010650-H1.0__A

Example
-------
 ::

    align_batch_ALOS2_SCAN.csh align.in                      


