.. index:: ! preproc_batch_tops_esd.csh

**************************
preproc_batch_tops_esd.csh
**************************

Synopsis
--------
**preproc_batch_tops_esd.csh** *data.in dem.grd mode esd_mode* 

Description
-----------
**preproc_batch_tops_esd.csh** preprocess and align a set of tops images in data.in, precise orbits required. Uses Enhanced Spectral Diversity.  

Mode 1 outputs a baseline.ps file which plots a baseline-time plot, which helps you choose a master image from your batch of files. In addition it creates an **align_table.ra** which contains the information for precise geometric alignment. 

Mode 2 produces the final, *aligned* .SLC files along with their respective .PRM and .LED files. Note that all files are aligned to the image listed in the first line of the *data.in* input file, so ensure that the line is your chosen master image before beginning mode 2 processing.


Required Arguments
------------------

*data.in*     

	Input file list of specific SAFE measurement file root names and their respective orbit files, formatted as below. To automatically create data.in use :doc:`prep_data.csh` or :doc:`prep_data_linux.csh` . Ensure that the first line listed in your data.in file is your master image (prep_data.csh does not do this for you, it must be done manually). 
             
	Format of data.in:

                    image_name:orbit_name

	*example of data.in for TOPS mode data:*

		s1a-iw1-slc-vv-20150626...001:s1a-iw1-slc-vv-20150626...001:s1a-iw1-slc-vv-20150626...001:S1A_OPER_AUX_POEORB_V20150601_20150603.EOF

		s1a-iw1-slc-vv-20150715...001:s1a-iw1-slc-vv-20150715...001:s1a-iw1-slc-vv-20150715...001:S1A_OPER_AUX_POEORB_V20150625_20150627.EOF


*dem.grd*    

	DEM file located in the topo folder must be linked here

*mode*       

	Processing mode. mode = 1 prepares for alignment and creates a baseline-time.ps plot to choose a master image, while mode=2 does the actual alignment (user-chosen master image must be promoted to the first line in data.in before mode 2 is run).

*esd_mode*

	0 for average, 1 for median, 2 for interpolation


Example
-------
 ::

    preproc_batch_tops_esd.csh data.in dem.grd 1 1 


References
----------

Xu, X., Sandwell, D.T., Tymofyeyeva, E., González-Ortega, A. and Tong, X., 2017. Tectonic and Anthropogenic Deformation at the Cerro Prieto Geothermal Step-Over Revealed by Sentinel-1A InSAR. IEEE Transactions on Geoscience and Remote Sensing. https://doi.org/10.1109/TGRS.2017.2704593 
