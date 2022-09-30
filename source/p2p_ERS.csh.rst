.. index:: ! p2p_ERS.csh    

***********
p2p_ERS.csh   
***********

Synopsis
--------
**p2p_ERS.csh** *master_stem aligned_stem configuration_file*

Description
-----------
**p2p_ERS.csh** is a processing script for producing an interferogram from ERS data 

Place the raw data in a directory called **raw** and a dem.grd file in a parallel directory called **topo**. The raw data should have 4 files: two with a suffix of .dat and two with a suffix of .ldr.

Execute this command at the directory location above **raw** and **topo**.

The file dem.grd is a dem that completely covers the SAR frame, or is larger than the SAR frame. If the dem is omitted then an interferogram will still be created, but there will not be a geocoded output. A custom dem.grd file can be made at the website: http://topex.ucsd.edu/gmtsar

Required Arguments
------------------

*master_stem*

	Name stem of the master or reference image

*aligned_stem*

	Name stem of the aligned or secondary image

*configuration_file*

	Name of configuration file for interferogram processing. A default file can be generated using :doc:`pop_config.csh`


Example
-------
 ::

    p2p_ERS.csh ERS_127_2943_61103 ERS2_127_2943_65111 config.ers.txt 
