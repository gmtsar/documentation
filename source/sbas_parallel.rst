.. index:: ! sbas_parallel                 

************      
sbas_parallel              
************      

Synopsis
--------
**sbas_parallel** *intf.tab scene.tab N S xdim ydim [-atm ni] [-smooth sf] [-wavelength wl] [-incidence inc] [-range -rng] [-rms] [-dem]* 


Description
-----------
**sbas_parallel** Coherence-based Small Baseline Subset time series processing (see references for theory) in parallel

FOR PARALLEL PROCESSING: Before run: set the environment variable OMP_NUM_THREADS to a proper number that fits your machine (you need to know how many cores and threads you have on your machine, as this process can easily overload the memory and processing capability of a machine).
    
Input: 

  intf.tab             --  list of unwrapped (filtered) interferograms (can be created with :doc:`prep_sbas.csh`)

                           format:   unwrap.grd  corr.grd  ref_id  rep_id  B_perp 

  scene.tab            --  list of the SAR scenes in chronological order (can be created with :doc:`prep_sbas.csh`)

                           format:   scene_id   number_of_days 

                           note:     the number_of_days is relative to a reference date 

  N                    --  number of the interferograms

  S                    --  number of the SAR scenes 

  xdim and ydim        --  dimension of the interferograms

  -smooth sf           --  smoothing factors, default=0 

  -atm ni              --  number of iterations for atmospheric correction, default=0(skip atm correction) Tip: ni=3 is a good place to start 

  -wavelength wl       --  wavelength of the radar wave (m) default=0.236 

  -incidence theta     --  incidence angle of the radar wave (degree) default=37 

  -range rng           --  range distance from the radar to the center of the interferogram (m) default=866000 

  -rms                 --  output RMS of the data misfit grids (mm): rms.grd

  -dem                 --  output DEM error (m): dem.grd 


Output: 

  disp_YYYY.DDD.grd    --  cumulative displacement time series (mm) grids (file name as year.dayofyear format)

  vel.grd              --  mean velocity (mm/yr) grid


References: 
Berardino P., G. Fornaro, R. Lanari, and E. Sansosti, “A new algorithm for surface deformation monitoring based on small baseline differential SAR interferograms,” IEEE Trans. Geosci. Remote Sensing, vol. 40, pp. 2375–2383, Nov. 2002. 

Schmidt, D. A., and R. Bürgmann 2003, Time-dependent land uplift and subsidence in the Santa Clara valley, California, from a large interferometric synthetic aperture radar data set, J. Geophys. Res., 108, 2416, doi:10.1029/2002JB002267, B9. 

Tong, X. and Schmidt, D., 2016. Active movement of the Cascade landslide complex in Washington from a coherence-based InSAR time series method. Remote Sensing of Environment, 186, pp.405-415. 

Tymofyeyeva, E. and Fialko, Y., 2015. Mitigation of atmospheric phase delays in InSAR data, with application to the eastern California shear zone. Journal of Geophysical Research: Solid Earth, 120(8), pp.5952-5963.

Xu, X., Sandwell, D. T., Tymofyeyeva, E., González-Ortega, A., & Tong, X. (2017). Tectonic and anthropogenic deformation at the Cerro Prieto geothermal step-over revealed by Sentinel-1A InSAR. IEEE Transactions on Geoscience and Remote Sensing, 55(9), 5284-5292. https://doi.org/10.1109/TGRS.2017.2704593


Example
-------
    **sbas_parallel** intf.tab scene.tab 88 28 700 1000 



