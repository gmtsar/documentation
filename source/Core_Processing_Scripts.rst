.. index:: ! Core_Processing_Scripts

***********************
Core Processing Scripts
***********************

All-in-One Interferogram Pair Processing
----------------------------------------

The following scripts accomplish all steps of the interferogram calculation
process in one run, depending on your dataset.  

   * :doc:`p2p_processing.csh`
   * :doc:`p2p_ALOS2_SCAN_Frame.csh`
   * :doc:`p2p_ALOS2_SCAN_SLC.csh`
   * :doc:`p2p_ENVI.csh`
   * :doc:`p2p_ERS.csh`
   * :doc:`p2p_S1_TOPS_Frame.csh`
   * :doc:`pop_config.csh`

Interferogram Processing, Step-by-Step
--------------------------------------

The following scripts are broken down into the steps of interferogram processing,
starting with preprocessing the data and then aligning the secondary image to the 
reference image, creating the topo_ra.grd (topography in radar coordinates), followed
by calculating the interferogram and filtering it, unwrapping the interferogram,
and geocoding that interferogram to view it in latitude-longitude coordinates.

Stage 1: Preprocessing 
----------------------
.. panels::

    Scripts
    ^^^^^^^
    
    * :doc:`pre_proc.csh`

    ---

    C Modules
    ^^^^^^^^^

    * :doc:`make_s1a_tops`
    * :doc:`make_s1a_tops_6par`
    * :doc:`make_slc_csk`
    * :doc:`make_slc_rs2`
    * :doc:`make_slc_s1a`
    * :doc:`make_slc_tsx`
    * :doc:`ALOS_pre_process`
    * :doc:`ALOS_pre_process_SLC`
    * :doc:`ALOS_pre_process_SS`
    * :doc:`ENVI_pre_process`
    * :doc:`ENVI_SLC_pre_process`
    * :doc:`ERS_pre_process`
    

Stage 2: Alignment
------------------

.. panels::

    Scripts
    ^^^^^^^
    
    * :doc:`sarp.csh`
    * :doc:`fitoffset.csh`
    * :doc:`align.csh` 
    * :doc:`align_ALOS2_SCAN.csh` 
    * :doc:`align_ALOS_SLC.csh` 
    * :doc:`align_SAT.csh`
    * :doc:`align_tops.csh` 
    * :doc:`align_tops_esd.csh` 

    ---

    C Modules
    ^^^^^^^^^
    * :doc:`esarp`
    * :doc:`SAT_baseline`
    * :doc:`xcorr`
    * :doc:`resamp`

Stage 3: Back Geocoding & Making topo_ra.grd
--------------------------------------------
.. panels::

    Scripts
    ^^^^^^^
    
    * :doc:`dem2topo_ra.csh`
    * :doc:`dem2topo_ra_ALOS2.csh`

    ---

    C Modules
    ^^^^^^^^^

    * :doc:`SAT_llt2rat`


Stage 4: Interferometry & Filtering
-----------------------------------
.. panels::

    Scripts
    ^^^^^^^
    
    * :doc:`intf.csh`
    * :doc:`intf_tops.csh`
    * :doc:`filter.csh`

    ---

    C Modules
    ^^^^^^^^^

    * :doc:`phasediff`
    * :doc:`conv`


Stage 5: Unwrapping Interferograms 
----------------------------------
.. panels::

    Scripts
    ^^^^^^^
    
    * :doc:`snaphu.csh`
    * :doc:`snaphu_interp.csh`
    * :doc:`landmask.csh`
    * :doc:`landmask_ALOS2.csh`

    ---

    C Modules
    ^^^^^^^^^

    * :doc:`snaphu`


Stage 6: Geocoding to Latitude-Longitude
----------------------------------------
.. panels::

    Scripts
    ^^^^^^^
    
    * :doc:`geocode.csh`
    * :doc:`proj_ra2ll.csh`
    * :doc:`grd2kml.csh`

    ---

    C Modules
    ^^^^^^^^^


Optional Correction Tools
-------------------------
.. panels::

    Scripts
    ^^^^^^^
    
    * :doc:`estimate_ionospheric_phase.csh`
    * :doc:`MAI_processing.csh`
    * :doc:`tide_correction.csh`

    ---

    C Modules
    ^^^^^^^^^

    * :doc:`split_spectrum`
    * :doc:`split_aperture`
    * :doc:`solid_tide`

Data Manipution & Geometric Tools
---------------------------------
.. panels::

    Scripts
    ^^^^^^^
    
    * :doc:`create_frame_tops.csh`
    * :doc:`samp_slc.csh`

    ---

    C Modules
    ^^^^^^^^^

    * :doc:`assemble_tops`
    * :doc:`stitch_tops`
    * :doc:`ALOS_merge`
    * :doc:`ALOS_mosaic_ss`
    * :doc:`ALOS_fbd2fbs`
    * :doc:`ALOS_fbd2fbs_SLC`
    * :doc:`merge_swath`
    * :doc:`cut_slc`
    * :doc:`SAT_look`
    * :doc:`nearest_grid`


