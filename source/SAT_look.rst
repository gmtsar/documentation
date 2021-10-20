.. index:: ! SAT_look

********
SAT_look
********

Synopsis
--------
**SAT_look** *master.PRM* [-bo[s|d]] < *input_table* > *output_table*

Description
-----------
**SAT_look** reads in parameters specified in *master.PRM* (from the radar image as your reference 
for alignment), the corresponding *led_file*, the 3-column *input_table*, and create 6-column output 
to *output_table*

 master.PRM     -  parameter file for master image and points to LED orbit file 

 input_table    -  lon, lat, elevation(above ellipsoid) [ASCII] 

 output_table   -  lon, lat, elevation(above reference radius in PRM), look_E, look_N, look_U, [ASCII default] 

 -bos or -bod   -  binary single or double precision output 



Example
-------
    **SAT_look** master.PRM < topo.llt > topo.lltn 