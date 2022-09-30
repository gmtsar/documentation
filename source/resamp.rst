.. index:: ! resamp               

******      
resamp            
******      

Synopsis
--------
**resamp** *master.PRM aligned.PRM new_aligned.PRM new_aligned.SLC intrp*


Description
-----------
**resamp**                   

Required Arguments
------------------

*master.PRM*        

	PRM for master image 

*aligned.PRM*         

	PRM for aligned image 

*new_aligned.PRM*     

	PRM for aligned image 

*new_aligned.SLC*     

	SLC for aligned image 

*intrp*             

	Interpolation method: 1-nearest; 2-bilinear; 3-biquadratic; 4-bisinc    

Example
-------
 ::

    resamp master.PRM aligned.PRM aligned_new.PRM aligned_new.SLC 1 



