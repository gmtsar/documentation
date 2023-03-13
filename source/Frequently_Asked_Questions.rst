.. index:: ! Frequently Asked Questions

**************************
Frequently Asked Questions             
**************************

Here, we have compiled some of the most commonly asked questions, and
we have grouped them by catagory.

General Questions
-----------------

.. dropdown:: How can I get East/North/Up from my interferogram(s)?

    There is no easy way to do this due to the fact that at most we only have 
    two look directions from our interferograms (we cannot go from 2D to 3D without
    another source of information).

    One can calculate approximate East-West and Vertical displacements by 
    completing a decomposition of both ascending and descending data. This can be done
    in a few different ways (check the literature for different methods), but a simple
    approximation can be accomplished like the following:

       * Obtain the ascencing and descending data for, say, a LOS velocity map
       * Use gmt grdsample to coregister them to the same grid size
       * Use the following gmt grdmath equations to calculate approximate vertical and east-west:

     ::
   
        gmt grdmath asc.grd des.grd ADD 2 DIV $cos_v DIV = vert.grd
        gmt grdmath des.grd asc.grd SUB 2 DIV $cos_e DIV = horizontal.grd 

     where **$cos_v** is the cosine of your average vertical look angle and 
     **$cos_e** is the cosine of your average east look angle (check out :doc:`SAT_look` to
     help calculate look angles)

     For a more exact decomposition, you may have to do things pixel-by-pixel in an inversion. 


.. dropdown:: How can I convert longitude/latitude to radar coordinates?

    Points or Lists of Points: Use :doc:`SAT_llt2rat` and note that you should
    extract height information from your DEM file.

    Grids:  Use :doc:`proj_ll2ra.csh` and note that you will need to locate
    your **trans.dat** file to accomplish this coversion. 

    To go the opposite direction, check out :doc:`proj_ra2ll.csh` or the ascii
    version :doc:`proj_ra2ll_ascii.csh`.

.. dropdown:: How can I combine data from multiple tracks? 

    Since look angle changes from track to track, it is normal to have some jumps
    from one track to another. There isn't a simple way to combine tracks together, but
    the best way to do a combination is to do so on a modeling level (e.g., complete a fault
    slip inversion).

.. dropdown:: What is this "if: Badly formed number" error I'm seeing?

    This is usually caused by having some hidden special characters in your run  
    script (a common culprit is the "^M" from Windows systems).

    As a possible fix, try eliminating the special characters in the specific script.
    For example, if the local script "prep_sbas.csh" was spitting out this error, try:

     ::

        perl -pe 's/\r/\n/'g prep_sbas.csh > edit_prep_sbas.csh

    to remove the special characters at the ends of the lines.


Interferogram-related Questions
-------------------------------

.. dropdown:: Is my interferogram good or bad?

    This is a case-by-case answer, but usually a "good" interferogram is one
    that you can clearly see a signal (usually represented by a fringe or by
    areas of concentrated colors of the color map).
 
    A "bad" interferogram can look very different -- if there is a lot of 
    decorrelation in your image (e.g., is there a lot of pixelated area, or
    area that has been removed completely?) this can make it difficult to see
    any signal of interest.  


.. dropdown:: What is in my interferogram?

    This is a case-by-case answer, but an interferogram is usually going to contain
    some element of displacement (whether interseismic plate motion, or subsidence, or
    some other displacement), represented by fringes, and some element of noise (usually
    atmospheric effects). The noise can often completely mask small displacement signals,
    so take care in interpreting possible signals.

.. dropdown:: How do I correct for atmospheric noise in my interferogram?

    There is no one-size-fits-all answer to this question because correcting and/or
    removing noise caused by atmosperic delay is an area of active research. The amount
    or magnitude of atmospheric noise depends heavily on where your interferogram is.

    One possible choice is to use outside data or weather models to try correcting it.
    There are a variety of these corrects available, but a common one to try is the
    GACOS correction: http://www.gacos.net/  

    Correcting with GNSS data can also remove long-wavelength atmospheric noise
    (see :doc:`correct_insar_with_gnss.csh` to learn how to use), but depends on the
    amount and distribution of GNSS stations in your study area (you will likely need ~4
    or more stations to perform the correction well).


Time Series Questions
---------------------

.. dropdown:: Why is my sbas time-series (disp_YYYYDOY.grd and vel.grd) blank?

    This often happens because there is single NaN pixel in the first column of your 
    input data to the sbas program. To fix this, instead of using a single threshold
    for your coherence (snaphu_threshold), calculate a correlation grid stack (average
    all your correlation grids (corr.grd)) and compute the mean (see :doc:`stack_corr.csh` )
    and then create a mask to mask out any pixels that do not meet the threshold you want.
    Once you create a mask, copy that mask to the name **mask_def.grd** and ensure it is 
    linked to your interferogram directories before you unwrap. 

    To make a mask with a chosen coherence threshold of 0.075:
 
     ::
   
        gmt grdmath corr_stack.grd 0.075 GE 0 NAN = mask_def.grd

     

.. dropdown:: How do I set a reference point in my time series?

    To set a reference point in your time series, you need to select a point location
    within your interferogram coverage area that has stable deformation over time (e.g.,
    try not to select a point that is in an area of large subsidence or large displacements).
    Once you have selected your point, what you need to do is subtract the LOS displacement value
    at that point in the interferogram, from the rest of the interferogram, essentially zero-ing 
    out your chosen point. Then do this for all your interferograms, at the same point in each one.

    For one interferogram, with your chosen point in range azimuth in a file called refpoint.ra
    (see SAT_llt2rat to convert longitude/latitude to range azimuth)

     ::
       
       gmt grdtrack refpoint.ra -Gunwrap.grd 
      
    
    Then, the value extracted by grdtrack needs to be removed from your interferogram, for example:

     ::
    
       gmt grdmath unwrap.grd [insert_value_here] SUB = ref_unwrap.grd

    
    This is a great place to use a for loop in whatever scripting language you're comfortable with.

    As an example, in bash:    

     ::
    
       for line in $( cat intf.list ); do
           echo "Working on pair ${line}..."
           point=$( gmt grdtrack refpoint.ra -G${line}/unwrap.grd | awk '{print $3}' )
           gmt grdmath ${line}/unwrap.grd ${point} SUB = ${line}/ref_unwrap.grd
       done

Data Questions
--------------

.. dropdown:: How do I get the right orbit file?

    If you are working with Sentinel-1 data, check out the tool :doc:`download_sentinel_orbits.csh`
    or :doc:`download_sentinel_orbits_linux.csh` which will download either the 
    precise orbits (preferred and recommended) or the resituted orbits (preliminary orbits,
    necessary for only most recent data in the last ~10 days).

    The trick to ensuring you have the correct orbit files is to compare the 
    data coverage time delineated by the last two dates in the filename (the first
    date in the file name is when the file was uploaded to the database). These
    second two dates (and times in UTC!) must cover the collection time of your SAR
    image (the collection time is listed in the filename for Sentinel-1 data).

    For example, if you have this SAR data file:
    S1A_IW_SLC__1SSV_20150526T014935_20150526T015002_006086_007E23_679A.SAFE

    You would need to download an orbit file with these dates in the last two dates in the filename:
    S1A_OPER_AUX_POEORB_OPOD_20210307T064730_V20150525T225944_20150527T005944.EOF

.. dropdown:: Where can I get GNSS data?

    There are multiple locations where you can obtain GNSS time series 
    or velocities. For newer users we recommend using a map-based application
    to select GNSS stations in your study area and then downloading the time 
    series or velocities for each station. Check out the following links. 
    Different catalogs can have different station datasets available, so feel
    free to check both for your area:

         * NASA MEaSUREs ESESES MGViz GNSS catalog map:
         * http://mgviz.ucsd.edu/?mission=ESESES

         * University of Nevada Reno (UNR) Nevada Geodetic Laboratory MAGNET map:
         * http://geodesy.unr.edu/NGLStationPages/gpsnetmap/GPSNetMap.html

    For downloading MEaSUREs time series, visit the SOPAC Displacement time 
    series webpage at http://sopac-csrc.ucsd.edu/index.php/displacements/ . 
    Here you can learn about the various products available. Click on Western 
    North America (WNAM) if your study area is in North America and Global if you’re 
    working internationally to get to the direct download product listing. You may 
    have to enter a username= “anonymous” and password= [your email address] 
    There are many choices, but we recommend using the 
    Clean_TrendNeuTimeSeries_comb_YYYYMMDD.tar.gz or 
    Filter_TrendNeuTimeSeries_comb_YYYYMMDD.tar.gz for comparing to InSAR time series. 
    When you download this file, it will contain all stations in the WNAM/Global network(s), 
    and you can select the particular station files you are interested in and unzip them. 
    Each station file contains the displacement time series, as well as the estimated 
    parameters, which are listed in the header at the top (including the velocity). 

    The MEaSUREs time series also has a list of velocities for all the stations they
    process, located here: http://sopac-csrc.ucsd.edu/index.php/velocities/ 
    (click on “Station Velocities”)

    For downloading from UNR MAGNET, see their documentation page: 
    http://geodesy.unr.edu/index.php  

    *One word of warning--make sure to read the documentation provided by whatever* 
    *data center you are using, so you understand, for example, which column is which* 
    *and what reference frame the data are processed in].*


