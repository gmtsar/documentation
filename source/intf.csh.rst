.. index:: ! intf.csh             

********      
intf.csh          
********      

Synopsis
--------
**intf.csh** *ref.PRM rep.PRM [-topo topogrd] [-model modelgrd]*


Description
-----------
**intf.csh** calculates an interferogram between two SLC images

Required Arguments
------------------
 
*ref.PRM*      

	Reference or master image .PRM file 

*rep.PRM*      

	Repeat/secondary image .PRM file


Optional Arguments
------------------

**-topo**  *topogrid*    

	Topo grid in radar coordinates (topo_ra.grd)

**-model**  *modelgrd*   

	Mode grid file
    
The dimensions of topogrd and modelgrd should be compatible with SLC file.


Example
-------
 ::

    intf.csh IMG-HH-ALPSRP055750660-H1.0__A.PRM IMG-HH-ALPSRP049040660-H1.0__A.PRM -topo topo_ra.grd 



