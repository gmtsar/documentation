.. index:: ! Batch_Interferograms

********************
Batch_Interferograms 
********************

This page covers the necessary set up and details for each step of the
batch processing interferogram workflow for non-Sentinel-1 data:

    * Selecting pairs  
    * Preparing a configuration file
    * Running :doc:`intf_batch.csh` to test settings    

Selecting Pairs
---------------

The first thing you need to do to produce your batch of interferograms is to decide which
interferograms you want to include in your batch or your time series. To do this, you
need to select a temporal baseline threshold and a spatial baseline threshold (in other words
you need to decide how long your longest interferograms will be apart in space and in time).

To calculate your list of interferogram pairs, you can use the tool :doc:`select_pairs.csh`
For example, in your raw directory, run:

 ::

    select_pairs.csh baseline_table.dat 50 100

This command will produce the file intf.in that includes all image pairs with a temporal baseline
smaller than 50 days, and a perpendicular spatial baseline smaller than 100 meters.

The file intf.in will list these pairs like this, for example, for ALOS data:

 ::

      IMG-HH-ALPSRP096010650-H1.0__A:IMG-HH-ALPSRP236920650-H1.0__A
      IMG-HH-ALPSRP089300650-H1.0__A:IMG-HH-ALPSRP096010650-H1.0__A
      IMG-HH-ALPSRP089300650-H1.0__A:IMG-HH-ALPSRP236920650-H1.0__A

Preparing a configuration file
------------------------------

Ensure that you have a batch_tops.config file in your track level directory. If you don’t have one
use :doc:`pop_config.csh` to generate one for your satellite data type.

The batch_tops.config file is the file that contains all of your processing parameter settings, and it is
where you will tell the processing programs how you want your interferograms prepared and calculated.

The first thing you need to edit is to put the date of your reference image in the "master_image" line:

 ::

    # Inside the file:
    # the namestem of the master image - REQUIRED
    master_image = 

Running intf.csh to test settings
---------------------------------

We recommend running a single interferograms in your batch first, in order to test your settings and
make sure everything is working properly. In addition, the first step (stage 1) calculates a large file
called topo_ra.grd, which is used to map topography into radar coordinates, and it only needs to be generated
once (and they you can change the stage number to 2).

To just run one test interferogram:

 ::

    # run one pair
    intf.csh IMG-HH-ALPSRP055750660-H1.0__A.PRM IMG-HH-ALPSRP049040660-H1.0__A.PRM -topo topo_ra.grd


Once that finishes, you should edit batch_tops.config again to set proc_stage = 2, which will enable
a full run of interferograms, and will skip making the topo_ra file which was created with this first run above.

Running Many interferograms
---------------------------

You can choose to run all your interferograms using :doc:`intf_batch.csh`.


