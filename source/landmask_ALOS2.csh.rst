.. index:: ! landmask_ALOS2.csh

******************
landmask_ALOS2.csh
******************

Synopsis
--------
**landmask_ALOS2.csh** *region_cut[min_range/max_range/min_azimuth/max_azimuth]*

Description
-----------
**landmask_ALOS2.csh** will make a landmask in radar coordinates for ALOS2.

Note: The region_cut can be specified in batch.config file

Required Arguments
------------------

*region_cut*

        Specify the range/azimuth of the grid you are making a landmask for.

Example
-------
 ::

    landmask_ALOS2.csh 0/10600/0/27648
