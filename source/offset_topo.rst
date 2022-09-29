.. index:: ! offset_topo          

***********      
offset_topo       
***********      

Synopsis
--------
**offset_topo** *amp_master.grd topo_ra.grd rshift ashift ns [topo_shift.grd]*


Description
-----------
**offset_topo** Determine topography offset                      

Required Arguments
------------------

*amp_master.grd*  

	Amplitude image of master 

*topo_ra.grd*     

	Topo in range/azimuth coordinates of master 

*rshift*          

	Guess at integer range shift 

*ashift*          

	Guess at integer azimuth shift 

*ns*              

	Integer search radius 

*topo_shift.grd*  

	Shifted topo_ra - optional, will be shifted by rshift, ashift     

Example
-------
 ::

    offset_topo 



