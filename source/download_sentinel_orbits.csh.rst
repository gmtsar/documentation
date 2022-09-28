.. index:: ! download_sentinel_orbits.csh

****************************
download_sentinel_orbits.csh
****************************

Synopsis
--------
**download_sentinel_orbits.csh** *safefilelist mode*

Description
-----------
**download_sentinel_orbits.csh** Downloads precise or restituted orbits for specific Sentinel-1 .SAFE data files

Precise orbits are generally the final calculated satellite orbits (and the preferred orbital information), while Restituted orbits are the preliminary and less precise orbit files. Only use restituted orbit files if the precise files are not yet available (there is generally a lag time of ~14 days).

Required Arguments
------------------


*safefilelist*

	List of SAFE files for which you wish to download orbits; must be listed with absolute path

	Format:

	 	absolutepathto/filename1.SAFE
	 	
		absolutepathto/filename2.SAFE


*mode*

	Mode specifies whether you want to download precise or restituted orbits. 

	Mode 1 = precise orbits (POEORB)

                 (most users should choose precise orbits)

	Mode 2 = temporary (restituted) orbits (RESORB)

            (only recent data (~last couple weeks) requires restituted orbits, because precise orbits are not yet finalized)



Example
-------
 ::

    download_sentinel_orbits.csh SAFEfile.list 1 
