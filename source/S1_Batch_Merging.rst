.. index:: ! S1_Batch_Merging

****************
S1_Batch_Merging 
****************

This page covers the necessary set up and details for merging 
subwaths of Sentinel-1 TOPS data in batch form:

    * Setting up to run :doc:`merge_batch.csh`
    * Running :doc:`merge_batch.csh`      

If you only processed one subswath, you do not need to merge anything.

Preparing Merge File
--------------------

In order to merge the Sentinel-1 TOPS mode subswath data into one image, you first need to prepare
a list of files that will be merged. You can do this using the :doc:`create_merge_input.csh`

 ::

    # Check out the tool usage page for specific features
    # remember to redirect the output to a merge.list file (otherwise it will print to screen)

    create_merge_input.csh intf.list .. 2 > merge.list

**CRITICAL NOTE** In order to merge with respect to the correct reference image, edit the output
merge.list by moving a line that contains your chosen reference image date to the first line in the file.
For example, if your reference date is 2018127, make sure to move a merge.list line that contains that date 
as the first image in the pair (e.g., 2018127_2018133) to the first line. 2018127_2018133 would work fine, but
note that 2018121_2018127 will not work (the reference date needs to be first).

Once you have an edited merge.list file, you should copy over your batch_tops.config file to the merge directory

 ::

    cd merge/
    cp ../F1/batch_tops.config .
    # also link the dem.grd file if it is not already linked
    ln -s ../topo/dem.grd


Running merge_batch.csh
-----------------------

From the merge directory, you can run the :doc:`merge_batch.csh` process:

 ::

    # Run in the background to produce a log file
    merge_batch.csh merge.list batch_tops.config >& merge_batch.log &

The output of this process should be interferogram directories in the merge/ directory that contain
merged coherence, mask (if relevant) and wrapped phase files (e.g., look for corr.grd, phase.grd, and phasefilt.grd).


**NOTE:** We recommend having a look at your merged grid products in order to make sure there are no merging errors
or to check if there are data issues. 

