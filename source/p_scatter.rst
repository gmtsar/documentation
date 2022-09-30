.. index:: ! p_scatter            

*********      
p_scatter         
*********      

Synopsis
--------
**p_scatter** *PRM_filelist fileout.grd mode*


Description
-----------
**p_scatter** Computes the average amplitude or persistent scattering function which is mu/(2*sig). The factor of 2 is used so the display_amplitude is not significantly changed.

Required Arguments
------------------

*PRM_filelist*       

	List of aligned SLCs 
   
*fileout.grd*        

	Output file either average amplitude or persistent_scatter 
   
*mode*               

	(0) amplitude; (1) persistent_scatter; (2) compute and apply persistent_scatter   
 

Example
-------
 ::

    p_scatter



