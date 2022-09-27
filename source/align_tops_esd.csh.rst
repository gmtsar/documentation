.. index:: ! align_tops_esd.csh   

******************      
align_tops_esd.csh
******************      

Synopsis
--------
**align_tops_esd.csh** *master_prefix master_orb_file aligned_s1a_prefix aligned_orb_file dem.grd [mode]*


Description
-----------
**align_tops_esd.csh** aligns TOPS-mode data (like Sentinel-1) with the ability to apply Enhanced Spectral Diversity                   
Be sure the tiff, xml, orbit and dem files are available in the local directory.
  
Required Arguments
------------------

*master_prefix*            

	The name stem of the master *.tiff/*.xml file, without the suffix
  
*master_orb_file*          

	The orbit file that covers the period of the master image collection time
        [use :doc:`download_sentinel_orbits.csh` or :doc:`download_sentinel_orbits_linux.csh` to obtain necessary orbit files]
  
*aligned_s1a_prefix*       

	The name stem of the secondary *.tiff/*.xml file, without the suffix
  
*aligned_orb_file*         

	The orbit file that covers the period of the secondary image collection time
        [use :doc:`download_sentinel_orbits.csh` or :doc:`download_sentinel_orbits_linux.csh` to obtain necessary orbit files]
  
*dem.grd*                

	DEM .grd file

Optional Arguments
------------------
  
*mode*

	set mode = 0 for constant sum correction, set mode = 1 for constant median correction, set mode = 2 for non-constant correction with mapping the residual azimuth shift

Example
-------
 ::

    align_tops_esd.csh s1a-iw3-slc-vv-20150526t014937-20150526t015002-006086-007e23-003 S1A_OPER_AUX_POEORB_OPOD_20150615T155109_V20150525T225944_20150527T005944.EOF.txt s1a-iw3-slc-vv-20150607t014937-20150607t015003-006261-00832e-006 S1A_OPER_AUX_POEORB_OPOD_20150627T155155_V20150606T225944_20150608T005944.EOF.txt dem.grd

Expected output: Output: S1_20150526_F3.PRM S1_20150526_F3.LED S1_20150526_F3.SLC S1_20150607_F3.PRM S1_20150607_F3.LED S1_20150607_F3.SLC


