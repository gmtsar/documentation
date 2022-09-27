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


Required Arguments
------------------

*master.PRM*       

	Parameter file for master image and points to LED orbit file 

*input_table*      

	Longitude, latitude, elevation((m) above ellipsoid) [ASCII] 

*output_table*     

	Longitude, latitude, elevation((m) above reference radius in PRM), look_East, look_North, look_Up, [ASCII default] 


Optional Argument
-----------------

*-bos*  or  *-bod*   

	Binary single (s) or double (d) precision output 



Example
-------
 ::

    SAT_look master.PRM < topo.llt > topo.lltn 
