.. index:: ! landmask.csh   

************
landmask.csh  
************

Synopsis
--------
**landmask.csh** *region_cut[min_range/max_range/min_azimuth/max_azimuth]*

Description
-----------
**landmask.csh** will make a landmask in radar coordinates.

Note: The region_cut can be specified in batch.config file

Required Arguments
------------------

*region_cut*

	Specify the range/azimuth of the grid you are making a landmask for.

Example
-------
 ::

    landmask.csh 0/10600/0/27648
