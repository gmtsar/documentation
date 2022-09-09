.. index:: ! create_frame_tops.csh 

**************
create_frame_tops.csh
**************

Synopsis
--------
**create_frame_tops.csh** *SAFE_filelist ****.EOF two_pins.ll [mode]*

Description
-----------
**create_frame_tops.csh** create one frame based on the two input frames, precise/restituted orbit is required         

  format of two_pins.llt (lon2/lat2 comes later than lon1/lat1 in orbit time):

    lon11 lat11 [lon12 lat12] [lon13 lat13]

    lon21 lat21 [lon22 lat22] [lon23 lat23]

    (drop more columns if you want subsath 2 and 3 to have different boundaries)


  outputs:

    new.SAFE --> datetime1-datetime2.SAFE

  Notes:
    The two input .SAFE file should be in time order, if the two_pin.llt is at wrong location, the program will output all the bursts. mode = 1, output vv; mode = 2, output vh; default is vv. 
    
    Files listed in SAFE_filelist should be the absolute path



Example
-------
**create_frame_tops.csh** 
