.. index:: ! intf_tops_parallel.csh

*******
intf_tops_parallel.csh
*******

Synopsis
--------
**intf_tops_parallel.csh** *intf.in batch_tops.config Ncores*

Description
-----------
**intf_tops_parallel.csh**  generate interferograms for a set of TOPS images in intf.in, in parallel using the user-specified number of cores; dem required in ./topo, and supermaster's name is required in batch_tops.config  

  Run interferogram jobs in parallel. Need to install GNU parallel first (e.g. sudo port install parallel).

  **Warning**: Familiarize yourself with how many cores your machine has (start with a small number first). 

  format of intf.in:

    master_image_stem:aligned_image_stem


  example of intf.in

    S1_20150628_ALL_F1:S1_20150720_ALL_F1

    S1_20150720_ALL_F1:S1_20150809_ALL_F1

  outputs:

    to ./intf_all

Note: batch_tops.config can be created using :doc:`pop_config.csh` with S1_TOPS as the satellite type

Example
-------
    **intf_tops_parallel.csh** intf.in batch_tops.config 5 
