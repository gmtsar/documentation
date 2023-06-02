.. index:: ! Time_Series_Processing_SBAS

***************************
Time_Series_Processing_SBAS
***************************

This page covers the necessary set up and details for running the
time series processing of batch unwrapped interferograms, using the
:doc:`sbas` software.

    * Setting up to run :doc:`sbas`
    * Running :doc:`sbas` or :doc:`sbas_parallel`      


Setting Up to Run SBAS
----------------------

*Prepare the Input Files*

First, you need to prepare the **scene.tab** and **intf.tab** files for running :doc:`sbas`.
To do this you can use the tool :doc:`prep_sbas.csh` as long as you have your intf.in and
baseline_table.dat files handy.

 ::

    # this assumes your unwrap.grd and corr.grd files are in ../merge/"date1_date2"/
    prep_sbas.csh intf.in baseline_table.dat ../merge unwrap.grd corr.grd

This will produce the scene.tab files (the list of dates in your time series) and the intf.tab file
(the list of interferogram phase and correlation files to be used in SBAS). It will also output a
basic/default sbas command structure for you.

Running SBAS
------------

Once you have your input files set up, you need to choose your sbas flags to produce the time series calculation
you want (see the :doc:`sbas` page for descriptions). 

Note that when you run sbas your machine will need a certain amount of memory to handle the calculation. The -mmap flag can 
help, but it will take longer to run. If you need to reduce the size of the calculation, you can choose to downsample your
input phase and correlation grids to a lower resolution.

*Running in parallel*

There is an option to run sbas in parallel (see :doc:`sbas_parallel`) if you have GNU parallel installed and if you have 
compiled the sbas_parallel program (see https://github.com/gmtsar/gmtsar/wiki/Compile-parallel-sbas-code for instructions). 


When sbas finishes, there should be a cumulative displacement grid (disp_xxxxxxx.grd) for every date in your scene.tab file,
a velocity grid (vel.grd), a DEM error grid (dem.grd, if you chose to output one), and an RMS misfit grid (rms.grd, if you
chose to output one). 

To extract a point time series from these grids, check out :doc:`extract_one_time_series.csh`. 


