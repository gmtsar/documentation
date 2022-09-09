.. index:: ! intf_tops.csh

*******
intf_tops.csh
*******

Synopsis
--------
**intf_tops.csh** *intf.in batch_tops.config*

Description
-----------
**intf_tops.csh**  generate interferograms for a set of tops images in intf.in, dem required in ./topo, and supermaster's name is required in batch_tops.config  

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
    **intf_tops.csh** intf.in batch_tops.config 
