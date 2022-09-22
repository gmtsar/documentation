.. index:: ! p2p_ALOS2_SCAN_Frame.csh

******************
p2p_ALOS2_SCAN_Frame.csh
******************

Synopsis
--------
**p2p_ALOS2_SCAN_Frame.csh** *Master_stem Aligned_stem config.alos2.txt parallel*

Description
-----------
The **p2p_ALOS2_SCAN_Frame.csh**  is a processing script for creating a interferogram 

Place the IMG-files and LED-files in a directory called `raw` and a `dem.grd` file in a parallel directory called `topo`. Execute this command at the directory location above `raw` and `topo`.

During processing, F1 - F5 and merge folder will be generated.
 
All SLCs will be upsampled to PRF 3350 and then processed.

Final results will be placed in the merge folder, with phase

	corr [unwrapped phase].

	parallel = 0-sequential  1-parallel 


Example
-------
    **p2p_ALOS2_SCAN_Frame.csh** IMG-HH-ALOS2234653650-180927-WBDR1.1__D IMG-HH-ALOS2236723650-181011-WBDR1.1__D config.alos2.txt 1

