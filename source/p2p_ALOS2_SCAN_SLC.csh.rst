.. index:: ! p2p_ALOS2_SCAN_SLC.csh

**********************
p2p_ALOS2_SCAN_SLC.csh
**********************

Synopsis
--------
**p2p_ALOS2_SCAN_SLC.csh** * *master_image aligned_image configuration_file subswatch*

Description
-----------
The **p2p_ALOS2_SCAN_SLC.csh** is a processing script for creating a interferogram using a pair of ALOS2 ScanSAR images.

Place the raw L1.1 data in a directory called **raw** and a dem.grd file in a parallel directory called **topo**. Execute this command at the directory location above **raw** and **topo**.

The file dem.grd is a dem that completely covers the SAR frame, or is larger than the SAR frame. If the dem is omitted then an interferogram will still be created, but there will not be a geocoded output. A custom dem.grd file can be made at the website: http://topex.ucsd.edu/gmtsar

Required Arguments
------------------

*master_image*

	Name stem of master or reference image

*aligned_image*

	Name stem of aligned or secondary image

*configuration_file*

	Name of the configuration file (.config). Generate a default config file using :doc:`pop_config.csh`

*subswatch*



Example
-------
 ::

    p2p_ALOS2_SCAN_SLC.csh  IMG-HH-ALOS2047033500-150407-WBDR1.1__D IMG-HH-ALOS2100853500-160405-WBDR1.1__D config.alos2.slc.txt 1

