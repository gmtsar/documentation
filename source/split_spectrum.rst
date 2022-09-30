.. index:: ! split_spectrum       

**************      
split_spectrum    
**************      

Synopsis
--------
**split_spectrum** *prm1 [split_half]*   


Description
-----------
**split_spectrum** program used to split range spectrum for SLC using a modified cosine filter

SLCs are bandpassed and then shifted to the center of the spectrum

Outputs **SLCH** and **SLCL**


Required Arguments
------------------

*prm1*

	Parameter file

*split_half*

	 Built for ALOS FBD FBS cases, put 1 for using half the spectrum



Example
-------
 ::

    split_spectrum



