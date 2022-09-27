.. index:: ! align.csh            

************      
align.csh         
************      

Synopsis
--------
**align.csh** *SAT master_name aligned_name [supermaster_name]*           


Description
-----------
**align.csh** aligns a secondary image to the specified master/reference image


Required Arguments
------------------

*SAT*

	Satellite (choose between ERS, ENVI, ALOS, or generic SAT)

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

    align.csh ALOS IMG-HH-ALPSRP055750660-H1.0__A IMG-HH-ALPSRP049040660-H1.0__A                      


