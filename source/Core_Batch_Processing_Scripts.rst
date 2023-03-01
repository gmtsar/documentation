.. index:: ! Core_Batch_Processing_Scripts

*****************************
Core Batch Processing Scripts
*****************************

Processing Batches of Interferograms Step-by-Step 
-------------------------------------------------

Batch processing of interferogram pairs involves processing many
interferograms at one time, rather then just doing one pair at a time.
The following scripts are listed for easy reference for each step of
batch processing, from gathering and organizing data, preprocessing that
data, aligning that data to a specific reference image, calculating
interferograms, and then unwrapping interferograms.

Additonally, we list the tools used to calculate time series from unwrapped
interferograms, as well as some helpful tools for data manipulation.

Preprocessing & Alignment
-------------------------  
.. panels::

    Scripts
    ^^^^^^^
    
    * :doc:`preproc_batch_tops.csh`
    * :doc:`preproc_batch_tops_esd.csh`
    * :doc:`pre_proc_batch.csh`
    * :doc:`pre_proc_batch_ALOS2_SCAN.csh`
    * :doc:`pre_proc_batch_ALOS_SLC.csh`
    * :doc:`align_batch.csh`


    ---

    C Modules
    ^^^^^^^^^

    * :doc:`sarp.csh`
    * :doc:`fitoffset.csh`
    * :doc:`align.csh` 
    * :doc:`align_ALOS2_SCAN.csh` 
    * :doc:`align_ALOS_SLC.csh` 
    * :doc:`align_SAT.csh`
    * :doc:`align_tops.csh` 
    * :doc:`align_tops_esd.csh` 
    * :doc:`esarp`
    * :doc:`SAT_baseline`
    * :doc:`xcorr`
    * :doc:`resamp`
   
Interferometry & Filtering 
-------------------------- 
.. panels::

    Scripts
    ^^^^^^^
    
    * :doc:`intf_batch.csh`
    * :doc:`intf_tops.csh`
    * :doc:`intf_tops_parallel.csh`
    * :doc:`select_pairs.csh`


    ---

    C Modules
    ^^^^^^^^^

    * :doc:`phasediff`
    * :doc:`conv`
   
Unwrapping
---------- 
.. panels::

    Scripts
    ^^^^^^^
    
    * :doc:`unwrap_parallel.csh`

    ---

    C Modules
    ^^^^^^^^^

    * :doc:`snaphu`
   
Time Series via SBAS
--------------------
.. panels::

    Scripts
    ^^^^^^^
    
    * :doc:`prep_sbas.csh`
    * :doc:`stack.csh`
    * :doc:`stack_corr.csh`

    ---

    C Modules
    ^^^^^^^^^

    * :doc:`sbas`
    * :doc:`sbas_parallel`
   

Optional Correction Tools
-------------------------

To apply these corrections, they need to either be applied within the batch
scripts, or performed pairwise through a loop of interferograms

.. panels::

    Scripts
    ^^^^^^^
    
    * :doc:`estimate_ionospheric_phase.csh`
    * :doc:`MAI_processing.csh`
    * :doc:`tide_correction.csh`
    * :doc:`correct_insar_with_gnss.csh`

    ---

    C Modules
    ^^^^^^^^^

    * :doc:`split_spectrum`
    * :doc:`split_aperture`
    * :doc:`solid_tide`

Tools for Gathering & Organizing Data
-------------------------------------
.. panels::

    Scripts
    ^^^^^^^
    
    * :doc:`organize_files_tops.csh`
    * :doc:`organize_files_tops_linux.csh`
    * :doc:`create_frame_tops.csh`
    * :doc:`download_sentinel_orbits.csh`
    * :doc:`download_sentinel_orbits_linux.csh`

    ---

    C Modules
    ^^^^^^^^^

    * :doc:`assemble_tops`
    * :doc:`stitch_tops`

Tools for Preparing Input Files & Merging Subswaths
---------------------------------------------------
.. panels::

    Scripts
    ^^^^^^^
    
    * :doc:`get_baseline_table.csh`
    * :doc:`prep_data.csh`
    * :doc:`prep_data_linux.csh`
    * :doc:`prep_sbas.csh`
    * :doc:`create_merge_input.csh`
    * :doc:`merge_batch.csh`
    * :doc:`merge_unwrap_geocode_tops.csh`

    ---

    C Modules
    ^^^^^^^^^
    
    * :doc:`ALOS_merge`
    * :doc:`merge_swath`
 
