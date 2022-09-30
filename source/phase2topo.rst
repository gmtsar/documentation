.. index:: ! phase2topo           

**********      
phase2topo        
**********      

Synopsis
--------
**phase2topo** *master.PRM topo_in.grd res_phase.grd topo_out.grd*


Description
-----------
**phase2topo** Compute residual topography  

Note the residual phase should be scaled by the perpendicular baseline (see :doc:`bperp`).    

Required Arguments
------------------

*master.PRM*      

	Master PRM files used for mapping 

*topo_in.grd*     

	Name of input topography in the radar co-ordinates of the master. 

*res_phase.grd*   

	Name of input phase per unit baseline

*topo_out.grd*    

	Name of output corrected topography in the radar co-ordinates of the master. 


Example
-------
 ::

    phase2topo



