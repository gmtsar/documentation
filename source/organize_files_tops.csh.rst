.. index:: ! organize_files_tops.csh

**************
organize_files_tops.csh
**************

Synopsis
--------
**organize_files_tops.csh** *filelist pins.ll mode*

Description
-----------
**organize_files_tops.csh** organize one track of S1A TOPS data, redefine frames, auto-download precise orbits; if restituted orbits are required, user must download separately 

file list:

    pth_filename1

    pth_filename2

    ......

pins.ll:
    lon1 lat1

    lon2 lat2

    ......

Note: 
    files listed in filelist should be the .SAFE directory with absolute path.
    mode = 1 will tell how many records are going to be generated. mode = 2 will do the organizing.


Example
-------
  **organize_files_tops.csh** SAFEfile.list T035_pins.ll 1 
