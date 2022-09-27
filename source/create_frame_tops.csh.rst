.. index:: ! create_frame_tops.csh 

*********************
create_frame_tops.csh
*********************

Synopsis
--------
**create_frame_tops.csh** *SAFE_filelist file.EOF two_pins.ll [mode]*

Description
-----------
**create_frame_tops.csh** create one frame based on the two input frames, precise/restituted orbit is required         
  
Outputs:

    new.SAFE --> datetime1-datetime2.SAFE

Required Arguments
------------------

*SAFE_filelist*

	List of SAFE file names, in time order, with absolute path

*.EOF*

	Respective .EOF orbit file for the images

*two_pins.ll*

	Contains the user-specified limits of the frame-to-be-created. If the two_pins.ll is at wrong location, the program will output all the bursts.

		*Format of two_pins.llt (the second pin (lon2/lat2) comes later than the first pin (lon1/lat1) in orbit time (check asc/des)):*

    			lon11 lat11 [lon12 lat12] [lon13 lat13]

    			lon21 lat21 [lon22 lat22] [lon23 lat23]

    		(add more columns if you want subsath 2 and 3 to have different boundaries)

Optional Argument
-----------------

*mode*
	
	Mode = 1, output vv; mode = 2, output vh; default is vv.



Example
-------
 ::

    create_frame_tops.csh SAFEfile.list S1A_OPER_AUX_POEORB_OPOD_20210307T064730_V20150525T225944_20150527T005944.EOF two_pins.ll  
