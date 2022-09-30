.. index:: ! stack_corr.csh      

**************
stack_corr.csh     
**************

Synopsis
--------
**stack_corr.csh** *list meancorr.grd* 

Description
-----------
**stack_corr.csh** compute the mean correlation from a stack of correlation grid files   

Required Arguments
------------------

*list*                  

	A list of corr.grd file names. The grid of the grd files must be consistent
  
*meancorr.grd*          

	Specify the output file name of the mean correlation grid 

Example
-------
 ::

    stack_corr.csh corr_grid.list corr_mean_stack.grd 
