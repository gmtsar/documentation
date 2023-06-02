.. index:: ! S1_Batch_Interferograms

***********************
S1_Batch_Interferograms 
***********************

This page covers the necessary set up and details for each step of the
batch processing interferogram workflow for Sentinel-1 data:

    * Selecting pairs  
    * Set up the **intf.in** file over desired subswaths        
    * Preparing a configuration file
    * Running :doc:`intf_tops.csh` to test settings    
    * Running :doc:`intf_tops_parallel.csh` 


Selecting Pairs
---------------

The first thing you need to do to produce your batch of interferograms is to decide which 
interferograms you want to include in your batch or your time series. To do this, you
need to select a temporal baseline threshold and a spatial baseline threshold (in other words
you need to decide how long your longest interferograms will be apart in space and in time).

To calculate your list of interferogram pairs, you can use the tool :doc:`select_pairs.csh`
For example, in the F1 (or other subswath) directory, run:

 ::
    
    # if you don't see your baseline_table.dat in F1, move it from your raw directory

    select_pairs.csh baseline_table.dat 50 100

This command will produce the file intf.in that includes all image pairs with a temporal baseline
smaller than 50 days, and a perpendicular spatial baseline smaller than 100 meters.

The file intf.in will list these pairs like this:

 ::

    S1_20180508_ALL_F1:S1_20180514_ALL_F1
    S1_20180508_ALL_F1:S1_20180526_ALL_F1
    S1_20180508_ALL_F1:S1_20180607_ALL_F1
    S1_20180508_ALL_F1:S1_20180520_ALL_F1

To view their baselines in plot form, open up baseline.ps and to calculate the number of pairs in intf.in
just use

 ::

    # output the number of lines in intf.in
    wc -l intf.in

Set up the intf.in file over desired subswaths
----------------------------------------------

Depending on which subswath you intend to process, you need to copy you intf.in in the first subswatch directory
to the other subswath directories you plan to process. We use the same list of pairs for all subswatchs in order
to process a consistent number and pairs of interferograms across subswaths. When you copy the intf.in file to
a different subswath, edit the file in the new directory to match its subswath number:

 ::

    # copy the intf.in file from F1 to subswaths F2 and F3
    cp intf.in ../F2
    cp intf.in ../F3

    cd ../F2
    vi intf.in
    # once in vi (or the text editor of your choice), replace the F1s with F2s
    # (e.g., in vi, enter ":%s/F1/F2/g" and hit return to use sed to replace text
    # do the same in the file in F3 (if processing)

Now you should have an intf.in file in every subswath directory you plan to process.

Preparing a configuration file
------------------------------

Ensure that there is a batch_tops.config file in each of the subswath directories you wish to process.

The batch_tops.config file is the file that contains all of your processing parameter settings, and it is
where you will tell the processing programs how you want your interferograms prepared and calculated.

The first thing you need to edit is to put the date of your reference image in the "master_image" line:

 ::

    # Inside the file:
    # the namestem of the master image - REQUIRED
    master_image = S1_20190318_ALL_F1

    # Do the same for every batch_tops.config file in each subswath you are processing


Then, you should check that these settings are set:

 ::

    # keep these numbers consistent across subswaths
    proc_stage = 1  # set stage to first produce the topo_ra.grd file
    shift_topo = 0  # don't shift topo_ra
    filter_wavelength = 200  # set the filter wavelength for your interferograms
    range_dec = 8   # set the output decimation of your interferograms in range direction
    azimuth_dec = 2 # set the output decimation of your interferograms in azimuth direction
    threshold_snaphu = 0  # 0 means do not unwrap 
    threshold_geocode = 0 # 0 means do not geocode right now

After that, the config file will have default parameters to calculate interferograms, but all can be
adjusted and changed to your liking (e.g., filter wavelength, region cut, image decimation)

Running intf_tops.csh to test settings
--------------------------------------

We recommend running a single interferograms in your batch first, in order to test your settings and
make sure everything is working properly. In addition, the first step (stage 1) calculates a large file 
called topo_ra.grd, which is used to map topography into radar coordinates, and it only needs to be generated
once (and they you can change the stage number to 2).

To just run one test interferogram:

 ::

    # grab one pair from intf.in
    head -1 intf.in > one.in

    # run that one pair
    intf_tops.csh one.in batch_tops.config

Once that finishes, you should edit batch_tops.config again to set proc_stage = 2, which will enable
a full run of interferograms, and will skip making the topo_ra file which was created with this first run above.

Running Many interferograms 
---------------------------

You can choose to run all your interferograms using :doc:`intf_tops.csh`, and run one after the other in
a for loop.

There is also the option of running :doc:`intf_tops_parallel.csh` and which can run many interferograms
in parallel on your machine. Please note that you will need to have GNU parallel installed, and you need to
know the number of cores your machine has (and how much memory). For each "thread" specified in the command
allow for one core and 5-8GB of memory. If you are on a lower memory machine (e.g., 64GB) we'd recommend  
starting with a low number (2-3) and seeing how that goes first. 

To run in parallel (with GNU parallel installed):

 ::

    intf_tops_parallel.csh intf.in batch_tops.config 5 >& itp.log &

This may take some time, depending on your computing power and number of interferograms

Interferograms and their corresponding directories will be output inside **intf_all/**.

**NOTE:** Repeat the above in each subswath directory you plan to process (including running stage 1 and changing to stage 2 afterwards). 
