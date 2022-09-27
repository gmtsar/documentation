.. index:: ! calc_dop_orb         

************      
calc_dop_orb      
************      

Synopsis
--------
**calc_dop_orb** *file.PRM  added.PRM  earth_radius  [doppler_centroid]*


Description
-----------
**calc_dop_orb**                       

Required Arguments
------------------
    
*file.PRM*         

	Input name of PRM file 

*new.PRM*          

	Output additional parameters to add to the PRM file 

*earth_radius*     

	Input set earth radius, 0 calculates radius 

Optional Argument
-----------------

*doppler_centroid*  

	No parameter calculates doppler. Use a value (e.g., 0.0) to force no calculation of doppler centroid


Example
-------
 ::

    calc_dop_orb 



