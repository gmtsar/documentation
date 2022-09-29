.. index:: ! intf_tops.csh

*************
intf_tops.csh
*************

Synopsis
--------
**intf_tops.csh** *intf.in batch_tops.config*

Description
-----------
**intf_tops.csh**  generate interferograms for a set of TOPS mode images listed in intf.in. A dem.grd file is required in a local ./topo directory, and the supermaster file name is required to be listed in batch_tops.config  

Final interferograms are output to a date1_date2 directory (YYYYDDD_YYYYDDD) inside the intf_all directory 

Required Arguments
------------------

*intf.in*

	List of image pairs for which to calculate interferograms

	Format of intf.in:

		master_image_stem:aligned_image_stem


	*example of intf.in*

		S1_20150628_ALL_F1:S1_20150720_ALL_F1

		S1_20150720_ALL_F1:S1_20150809_ALL_F1

*batch_tops.config*

	Configuration file for running interferograms. A default batch_tops.config can be created using :doc:`pop_config.csh` with S1_TOPS as the satellite type. Make sure to edit the batch_tops.config file to contain the chosen supermaster image name stem 

Example
-------
 ::

    intf_tops.csh intf.in batch_tops.config 
