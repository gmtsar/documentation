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

  list            --      a list of corr.grd file names
  
  meancorr.grd    --      output file name of the mean correlation grid 

  note that the grid of the grd files must be consistent



Example
-------
  **stack_corr.csh** corr_grid.list corr_mean_stack.grd 
