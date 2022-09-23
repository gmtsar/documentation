.. index:: ! download_sentinel_orbits_linux.csh

******************************
download_sentinel_orbits_linux.csh
******************************

Synopsis
--------
**download_sentinel_orbits_linux.csh** *safefilelist mode*

Description
-----------
**download_sentinel_orbits_linux.csh** Downloads precise or restituted orbits for specific Sentinel-1 *.SAFE data files

safefilelist:

    absolutepathto/filename1.SAFE

    absolutepathto/filename2.SAFE

    ......


mode:

    mode 1 = precise orbits (POEORB)

            (most users should choose precise orbits)

    mode 2 = temporary (restituted) orbits (RESORB)

            (only recent data (~last couple weeks) requires restituted

            orbits, because precise orbits are not yet finalized)

Note: 

  (1) Files listed in safefilelist should be the .SAFE directory with absolute path. 



Example
-------
**download_sentinel_orbits_linux.csh** SAFEfile.list 1 
