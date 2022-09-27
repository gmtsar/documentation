.. index:: ! align_ALOS2_SCAN.csh

********************
align_ALOS2_SCAN.csh
********************

Synopsis
--------
**align_ALOS2_SCAN.csh** *master_name aligned_name [supermaster_name]*                


Description
-----------
**align_ALOS2_SCAN.csh** aligns a specified image to a master/reference image 


Required Arguments
------------------

*master_name* 
	
	Name stem of master or reference image

*aligned_name*

	Name stem of aligned or secondary image

Optional Argument
-----------------

*supermaster_name*

	Name stem of the supermaster image. Only required if this is a secondary alignment.



Example
-------
 ::

    align_ALOS2_SCAN.csh IMG-HH-ALPSRP055750660-H1.0__A IMG-HH-ALPSRP049040660-H1.0__A                         


