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
InSAR data. Put the data and orbit files in the raw folder, put DEM in the topo folder and execute the script
The structure are as below with PRM and orbit files optional depending on the *SAT* option.

raw: radar_image_1 [PRM_file_1] [orbit_1] radar_image_2 [PRM_file_2] [orbit_2]

topo: dem.grd


The *SAT* needs to be specified, choices with in ERS, ENVI, ALOS, ALOS_SLC, ALOS2, ALOS2_SCAN, S1_STRIP, S1_TOPS, ENVI_SLC, CSK_RAW, CSK_SLC, TSX, RS2.
Make sure the files from the same date have the same stem, e.g. aligned_image.tif aligned_image.xml aligned_image.cos aligned_image.EOF, etc
If the configuration file is left blank, the script will generate one with default parameters using :doc:`pop_config.csh`

Example
-------
    **p2p_processing.csh** ALOS IMG-HH-ALPSRP055750660-H1.0__A IMG-HH-ALPSRP049040660-H1.0__A [config.alos.txt]

