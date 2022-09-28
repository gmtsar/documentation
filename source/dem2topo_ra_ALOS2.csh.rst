.. index:: ! dem2topo_ra_ALOS2.csh

*********************
dem2topo_ra_ALOS2.csh
*********************

Synopsis
--------
**dem2topo_ra_ALOS2.csh** *master.PRM dem.grd [xmin/xmax/ymin/ymax]*

Description
-----------
**dem2topo_ra_ALOS2.csh** converts a dem.grd file to a topo_ra.grd file for ALOS2 processing    


Required Arguments
------------------

*master.PRM*

	Parameter (PRM) file for the master or reference image

*dem.grd*

	DEM grid file

Optional Argument
-----------------

*xmin/xmax/ymin/ymax*

	If a you want to apply a region cut to your DEM/topo_ra grid, apply it here

Example
-------
 ::

    dem2topo_ra_ALOS2.csh supermaster.PRM dem.grd 
