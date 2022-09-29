.. index:: ! nearest_grid         

************      
nearest_grid      
************      

Synopsis
--------
**nearest_grid** *input.grd output.grd [search_radius]*

Description
-----------
**nearest_grid** Interpolation algorithm used within :doc:`snaphu_interp.csh`                      
   
  NaNs will be interpolated to its nearest neighbour 

Required Arguments
------------------

*input.grd*

	Input grid file

*output.grd*

	Output grid file

Optional Argument
-----------------

*search_radius*

	Distance used to search for non-Nan pixels in the area of the current pixel

Example
-------
 ::

    nearest_grid



