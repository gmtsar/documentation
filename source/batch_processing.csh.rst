.. index:: ! batch_processing.csh

********************
batch_processing.csh
********************

Synopsis
--------
**batch_processing.csh** *SAT master_image inputfile step [configuration_file]*

**NOTE: THIS SCRIPT IS STILL IN BETA-VERSION TESTING**

Description
-----------
**batch_processing.csh** completes batch processing for the specified satellite type, datafiles, and step number

Put the data and orbit files in the raw folder, put DEM in the topo folder

Make sure the files from the same date have the same stem, e.g. stem.tif stem.xml stem.cos stem.EOF, etc

If the configuration file is left blank, the program will generate one with default parameters


Required Arguments
------------------

*SAT*    

	The SAT needs to be specified, choices with in ERS, ENVI, ALOS, ALOS_SLC, ALOS2, ALOS2_SCAN
        S1_STRIP, S1_TOPS, ENVI_SLC, CSK_RAW, CSK_SLC, TSX, RS2, GF3
 
*master_image*  

	User needs to provide the master/reference image name stem

*inputfile*     

	Input file depends on the step you request processing for (steps 1-6 described below).

*step* 

        Details: The step could be 1-preprocessing, 2-alignment, 3-backgeocoding, 4-interferometry, 
        5-phase unwrapping, and 6-geocoding. For TOPS data, step 1 and 2 are done together. 

        **STEP 1**: preprocessing, inputfile should be a list of inputdata with or without orbit files, master_image should be in the first line
        NEED at least THREE records to run 
        e.g., for ALOS data, the list should be: (pick FBS to be master image)
        IMG-HH-ALPSRP160702940-H1.0__D 
        IMG-HH-ALPSRP200962940-H1.0__D 
        IMG-HH-ALPSRP268062940-H1.0__D 
        and for Sentinel-1 TOPS data, the list should be like:
        s1a-iw1-slc-vv-20150109t134413-20150109t134421-004095-004f4a-001:S1A_OPER_AUX_POEORB_OPOD_20210305T105546_V20150108T225944_20150110T005944.EOF 
        s1a-iw1-slc-vv-20150121t134413-20150121t134421-004270-005317-001:S1A_OPER_AUX_POEORB_OPOD_20210305T143838_V20150120T225944_20150122T005944.EOF 
        s1a-iw1-slc-vv-20150226t134412-20150226t134420-004795-005f58-001:S1A_OPER_AUX_POEORB_OPOD_20210306T014915_V20150225T225944_20150227T005944.EOF 

        **STEP 2**: alignment, inputfile should be a list of inputdata with master image in the first line 
        e.g., for ALOS data, the list should be like:
        NEED at least THREE records to run 
        IMG-HH-ALPSRP160702940-H1.0__D 
        IMG-HH-ALPSRP200962940-H1.0__D 
        IMG-HH-ALPSRP268062940-H1.0__D 
        and for Sentinel-1 TOPS data, this step could be skipped.
        For secondary alignment, run this step multiple times with -skip_master = 1, for secondary and tertiary alignment.

        **STEP 3**: backgeocoding, make sure DEM is in the topo directory, and PRM and LED file of the master image exist in the raw directory. 
        This only need to be run once for a stack of data.

        **STEP 4**: interferometry, inputfile should be a list of interferogram pairs 
        e.g., for ALOS data the list should be like:
        IMG-HH-ALPSRP160702940-H1.0__D:IMG-HH-ALPSRP200962940-H1.0__D 
        IMG-HH-ALPSRP160702940-H1.0__D:IMG-HH-ALPSRP268062940-H1.0__D 
        IMG-HH-ALPSRP200962940-H1.0__D:IMG-HH-ALPSRP268062940-H1.0__D
        and for Sentinel-1 TOPS data, the list should be like:
        S1_20150121_ALL_F1:S1_20150310_ALL_F1
        S1_20150121_ALL_F1:S1_20150403_ALL_F1
        S1_20150310_ALL_F1:S1_20150403_ALL_F1

        **STEP 5**: phase unwrapping, give the same input as step 4, and the script will go through every directory in intf_all and run 
        phase unwrapping using parameters specified in the config file

        **STEP 6**: geocoding, give the same input as step 4, and the script will go through every directory in intf_all and run geocoding



Optional Argument
-----------------

*[configuration_file]*

	If the configuration file is left blank, the program will generate one with default parameters


Example
-------
 ::

    batch_processing.csh ALOS IMG-HH-ALPSRP055750660-H1.0__A imagelist 1 config.alos.txt


