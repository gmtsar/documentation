.. index:: ! SAT_llt2rat

********
SAT_llt2rat
********

Synopsis
--------
**SAT_llt2rat** *master.PRM prec [-bo[s|d]] < inputfile > outputfile*

Description
-----------
**SAT_llt2rat** converts longitude/latitide/elevation to range/azimuth/elevation coordinates 

     master.PRM   -  parameter file for master image and points to LED orbit file 

     precise      -  (0) standard back geocoding, (1) - polynomial refinenent (slower) 

     inputfile    -  lon, lat, elevation [ASCII] 

     outputfile   -  range, azimuth, lon, lat, elevation [ASCII default] 

     -bos or -bod -  binary single or double precision output 


Example
-------
    **SAT_llt2rat** master.PRM 0 < topo.llt > topo.ratll
