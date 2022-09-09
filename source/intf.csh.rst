.. index:: ! intf.csh             

************      
intf.csh          
************      

Synopsis
--------
**intf.csh** *ref.PRM rep.PRM [-topo topogrd] [-model modelgrd]*


Description
-----------
**intf.csh** calculates an interferogram between two images

Input:
 
     ref.PRM   -   reference.PRM file 

     rep.PRM   -   repeat/secondary PRM file

     [-topo topogrid]  -  (optional) topo grid in radar coordinates (topo_ra.grd)

     [-model modelgrd] -  (optional) mode grid file
    
The dimensions of topogrd and modelgrd should be compatible with SLC file.


Example
-------
    **intf.csh** IMG-HH-ALPSRP055750660-H1.0__A.PRM IMG-HH-ALPSRP049040660-H1.0__A.PRM -topo topo_ra.grd 



