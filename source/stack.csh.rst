.. index:: ! stack.csh      

**************
stack.csh     
**************

Synopsis
--------
**stack.csh** *grid.list scale mean.grd std.grd*

Description
-----------
**stack.csh** compute the mean and standard deviations of a give stack of grid files

  grid.list   --  a list of grd file names

  scale       --  a scale factor put 1 if not scale

  mean.grd    --  output file name of the mean grid 

  std.grd     --  output file name of the standard deviation grid  

note that the grid of the grd files must be consistent

Example
-------
  **stack.csh** corr_grid.list 1 corr_stack.grd corr_stack_std.grd
