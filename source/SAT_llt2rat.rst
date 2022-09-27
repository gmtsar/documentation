.. index:: ! SAT_llt2rat

***********
SAT_llt2rat
***********

Synopsis
--------
**SAT_llt2rat** *master.PRM prec [-bo[s|d]] < inputfile > outputfile*

Description
-----------
**SAT_llt2rat** converts longitude/latitide/elevation to range/azimuth/elevation coordinates 


Required Arguments
------------------

*master.PRM*      

	Parameter file for master image and points to LED orbit file 

*precise*         

	(0) standard back geocoding, (1) - polynomial refinenent (slower) 

*inputfile*       

	Longitude, latitude, elevation (m) [ASCII] 

*outputfile*      

	Range, azimuth, longitude, latitude, elevation (m) [ASCII default] 

Optional Arguments
------------------

*-bos* or *-bod*    

	Binary single (s) or double (d) precision output 


Example
-------
 ::

    SAT_llt2rat master.PRM 0 < topo.llt > topo.ratll
