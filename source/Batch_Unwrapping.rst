.. index:: ! Batch_Unwrapping    

****************
Batch_Unwrapping     
****************

This page covers the necessary set up and details for each step of the
batch processing unwrapping workflow for interferograms:

    * Preparing to unwrap  
    * Preparing to run unwrap_intf.csh   
    * Running :doc:`unwrap_parallel.csh`

Preparing to Unwrap 
-------------------

Unwrapping interferograms can be a time-consuming and computationally intensive process, so
we recommend investing time on the front-end to make sure your unwrapping process goes smoothly
the first time. We list a couple steps you can take to help set yourself up for success.

*Checking Coherence/Correlation*

One critical thing to determine before unwrapping is how coherence varies in your region of interest,
as low coherence/correlation can lead to unwrapping errors and lower accuracy in displacement estimates.
Areas of good coherence are generally those that have flat, dry, unvegetated landscapes, while areas of poor
coherence can include areas with wet, highly vegetated landscapes (e.g., a rainforst, or area that experiences
lots of rain/surface moisture). 

First, if you have large bodies of water in your SAR images, one step you can take is to mask these out, as correlation
over water will be near zero. Check out :doc:`landmask.csh` to make a landmask using GMT coastlines and produce it in radar
coordinates. You can then link this landmask_ra.grd file to all your interferogram directories.

Second, if you have areas of low coherence in your study area, you can make a stacked coherence mask, which will mask out
any areas below a certain chosen threshold of coherence. This process can also be helpful in areas of high coherence just to
remove pixels with lower coherence. To make a stacked, average correlation grid, check out :doc:`stack.csh` and see
the example below.

 ::

    # to make a stacked, average correlation grid
    # in your merge directory (for S1_TOPS mode), or in your directory with all your interferograms
    ls 20*/corr.grd > corr.grd_list
    stack.csh corr.grd_list 1 corr_stack.grd std.grd  # if you have a couple hundred interfergrams this will take a while

When you plot your corr_stack.grd, you can see the spatial patterns of average coherence across all your data. From 
this image, you can estimate a threshold that will work for your area. Once you choose a good threshold that excludes
areas of low coherence and includes the areas of higher coherence, you can make a mask using GMT tools, for example:

 ::

    # 0.075 in the following command is a threshold of a coherence of 0.075
    # As a starting place, you could try a coherence of 0.1

    gmt grdmath corr_stack.grd 0.075 GE 0 NAN = mask_def.grd

Check what your mask looks like by plotting the mask_def.grd file. If it is masking out too much, lower the coherence
threshold, and if it is not masking out enough, raise the threshold value.

Once you settle on you chosen threshold, make a final mask_def.grd file, and link it to all your interferogram
directories.


*Checking for Merging Issues (S1_TOPS)*

If you are using S1_TOPS data and have merged multiple subswaths, check your merged data files to make sure
the merging process went smoothly, before trying to unwrap anything.

Unwrapping
----------

When you unwrap your interferograms, you will need to write a basic unwrapping script that links the 
necessary files and calls the proper tools. This script can look like this:

 ::
 
    vi unwrap_intf.csh
    #Include all lines between the lines
    --------------------------------

    #!/bin/csh -f
    # the input is a specific interferogram directory 
 
    cd $1
    ln -s ../mask_def.grd .  #if you are not using a mask_def.grd, comment this out
    ln -s ../landmask.grd .  # if you are not using a landmask.grd, comment this out
    
    snaphu_interp.csh 0.001 0  # check the snaphu_interp.csh page to choose proper values
    
    cd ../

    -------------------------------- 

This an example script that calls :doc:`snaphu_interp.csh` to complete unwrapping. To make sure
it is executable, change its permissions:

 ::

    # change the file to add "+x" executable to its permissions to be able to run it
   
    chmod +x unwrap_intf.csh

If your system cannot "find" this script, make sure it is in your $PATH variable.

Then, to run your unwrapping script, simply run:

 ::

    # give it an interferogram directory name
    unwrap_intf.csh 2018127_2018133 


Unwrapping Many Interferograms
------------------------------

You can run your unwrap_intf.csh script in a for loop through all your interferogram directories.

In addition, you can try running several unwrapping processes in parallel, with :doc:`unwrap_parallel.csh` which
will call "unwrap_intf.csh". You will need to have GNU parallel installed, and you will need to have a machine that
can handle the processing (make sure you know how many cores and how much memory you have). Allow ~1 core and 5-8GB   
of memory for each parallel thread you specify (if you have a lower memory machine, start low (2-3 threads)).

 ::
   
    unwrap_parallel.csh intf.list 4  # 4 threads, and a list of interferogram directories

This process will likely take some time to complete.

**NOTE** If one interferogram has not finished processing within 24 hours, double check that you are not trying unwrap
areas of bad data or large open areas of ocean as those can cause issues (check your phase.grd or phasefilt.grd).

**TROUBLE-SHOOTING NOTE**: If you are trouble-shooting, note that if you run unwrap_parallel.csh, it will produce a file
called unwrap.cmd, which will not get overwritten if you run unwrap_parallel.csh again. Either delete it or move it to 
a new name to you run everything with the correct command file.


