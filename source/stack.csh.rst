.. index:: ! stack.csh      

*********
stack.csh     
*********

Synopsis
--------
**stack.csh** *grid.list scale mean.grd std.grd*

Description
-----------
**stack.csh** compute the mean and standard deviations of a give stack of grid files

Required Arguments
------------------

*grid.list*    

	A list of grd file names. The grid of the grd files must be consistent.

*scale*         

	A scale factor put 1 if not scale

*mean.grd*      

	Specify the output file name of the mean grid 

*std.grd*       

	Specify the output file name of the standard deviation grid  

Example
-------
 ::

    stack.csh corr_grid.list 1 corr_stack.grd corr_stack_std.grd
