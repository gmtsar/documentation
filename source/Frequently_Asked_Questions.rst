.. index:: ! Frequently Asked Questions

**************************
Frequently Asked Questions             
**************************

Here, we have compiled some of the most commonly asked questions, and
we have grouped them by catagory.

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

Time Series Questions
---------------------

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

