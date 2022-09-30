.. index:: ! p2p_processing.csh

******************
p2p_processing.csh
******************

Synopsis
--------
**p2p_processing.csh** *SAT* *master_image* *aligned_image* [configuration_file] 

Description
-----------
The **p2p_processing.csh** script is a generic processing script for creating a interferogram using a pair of
InSAR data. Put the data and orbit files in **raw** folder, put the DEM (dem.grd) in a parallel **topo** folder and execute the script in the directory that contains both **raw** and **topo** .

The structure is shown below with PRM and orbit files optional depending on the *SAT* option.

 **raw** : radar_image_1 [PRM_file_1] [orbitfile_1] radar_image_2 [PRM_file_2] [orbitfile_2]

 **topo** : dem.grd


Required Arguments
------------------

*SAT*

	The *SAT* needs to be specified. Supported options are: ERS, ENVI, ALOS, ALOS_SLC, ALOS2, ALOS2_SCAN, S1_STRIP, S1_TOPS, ENVI_SLC, CSK_RAW, CSK_SLC, TSX, RS2.

*master_image*

	Name of the master or reference image

*aligned_image*

	Name of the aligned or secondary image

Make sure the files from the same date have the same stem, e.g. aligned_image.tif aligned_image.xml aligned_image.cos aligned_image.EOF, etc

Optional Argument
-----------------

*configuration_file*

	Name of configuration file for interferogram processing. A default file can be generated using :doc:`pop_config.csh` . If the configuration file is left blank, the script will generate one with default parameters using :doc:`pop_config.csh`

Example
-------
 ::

    p2p_processing.csh ALOS IMG-HH-ALPSRP055750660-H1.0__A IMG-HH-ALPSRP049040660-H1.0__A config.alos.txt

