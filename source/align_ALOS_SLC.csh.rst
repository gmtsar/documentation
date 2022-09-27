.. index:: ! align_ALOS_SLC.csh   

******************      
align_ALOS_SLC.csh
******************      

Synopsis
--------
**align_ALOS_SLC.csh** master_name aligned_name [supermaster_name]*           


Description
-----------
**align_ALOS_SLC.csh** aligns a secondary image to the specified master/reference image

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

    **align_ALOS_SLC.csh** IMG-HH-ALPSRP055750660-H1.0__A IMG-HH-ALPSRP049040660-H1.0__A                  


