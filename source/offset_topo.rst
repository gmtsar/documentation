.. index:: ! offset_topo          

************      
offset_topo       
************      

Synopsis
--------
**offset_topo** *amp_master.grd topo_ra.grd rshift ashift ns [topo_shift.grd]*


Description
-----------
**offset_topo** Determine topography offset                      

   amp_master.grd - amplitude image of master 

   topo_ra.grd    - topo in range/azimuth coordinates of master 

   rshift         - guess at integer range shift 

   ashift         - guess at integer azimuth shift 

   ns             - integer search radius 

   topo_shift.grd - shifted topo_ra - optional, will be shifted by rshift, ashift     

Example
-------
    **offset_topo** 



