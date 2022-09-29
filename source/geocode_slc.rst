.. index:: ! geocode_slc                     

***********      
geocode_slc       
***********      

Synopsis
--------
**geocode_slc** *your_file.PRM dem.grd*  


Description
-----------
**geocode_slc** *Sample slc to DEM and remove propogation delay* 


Required Arguments
------------------

*your_file.PRM*

	The parameter file for the SLC to be operated upon. Note that the .LED, .PRM and .SLC files of the same name stem must be in the same working directory as this is run.

*dem.grd*

	The DEM file


Example
-------
 ::

    geocode_slc S1_20170101_F1_ALL.PRM dem.grd 



