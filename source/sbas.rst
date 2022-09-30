.. index:: ! sbas                 

****      
sbas              
****      

Synopsis
--------
**sbas** *intf.tab scene.tab N S xdim ydim [-atm ni] [-smooth sf] [-wavelength wl] [-incidence inc] [-range -rng] [-rms] [-dem]* 


Description
-----------
**sbas** Coherence-based Small Baseline Subset time series processing (see references for theory)

The SBAS program outputs a cumulative displacement grid for every scene timestamp, with the filename *disp_YYYY.DDD.grd* where YYYY = year and DDD = Day of year. These are the final cumulative time series grids in units of millimeters.

In addition, the SBAS program outputs a final velocity field estimate, called **vel.grd**, which is the mean velocity in units of millimeters per year. 

If you choose to include the optional outputs **-dem** or **-rms** these will output additional products, i.e. the dem error estimate and the velocity rms estimate respectively (see below). 

    
Required Arguments
------------------

*intf.tab*               

	List of unwrapped (filtered) interferograms (can be created with :doc:`prep_sbas.csh`)

	Format:   unwrap.grd  corr.grd  ref_id  rep_id  B_perp 


*scene.tab*              

	List of the SAR scenes in chronological order (can be created with :doc:`prep_sbas.csh`)

	Format:   scene_id   number_of_days 

        Note:     the number_of_days is relative to a reference date 

*N*                      

	Number of the interferograms

*S*                      

	Number of the SAR scenes 

*xdim* and *ydim*          

	Dimension of the interferograms (Tip: use GMT's grdinfo tool to print the grid information (e.g. gmt grdinfo name.grd)

**-smooth**  *sf*             

	Smoothing factors, default=0 

**-atm** *ni*                

	Number of iterations for atmospheric correction, default=0(skip atm correction) Tip: ni=3 is a good place to start 

**-wavelength**  *wl*         

	Wavelength of the radar wave (m) default=0.236 

**-incidence** *theta*       

	Incidence angle of the radar wave (degree) default=37 

**-range**  *rng*             

	Range distance from the radar to the center of the interferogram (m) default=866000 

**-rms**                   

	Include this flag to output RMS of the data misfit grids (mm): rms.grd

**-dem**                   

	Include this flag to output the DEM error grid (m): dem.grd. 

	WARNING: This is an identical filename to a processing dem.grd, so make sure you do not have a dem.grd stored inside your working directory. 


Example
-------
 ::

    sbas intf.tab scene.tab 88 28 700 1000 


References
----------
 
Berardino P., G. Fornaro, R. Lanari, and E. Sansosti, “A new algorithm for surface deformation monitoring based on small baseline differential SAR interferograms,” IEEE Trans. Geosci. Remote Sensing, vol. 40, pp. 2375–2383, Nov. 2002. 

Schmidt, D. A., and R. Bürgmann 2003, Time-dependent land uplift and subsidence in the Santa Clara valley, California, from a large interferometric synthetic aperture radar data set, J. Geophys. Res., 108, 2416, doi:10.1029/2002JB002267, B9. 

Tong, X. and Schmidt, D., 2016. Active movement of the Cascade landslide complex in Washington from a coherence-based InSAR time series method. Remote Sensing of Environment, 186, pp.405-415. 

Tymofyeyeva, E. and Fialko, Y., 2015. Mitigation of atmospheric phase delays in InSAR data, with application to the eastern California shear zone. Journal of Geophysical Research: Solid Earth, 120(8), pp.5952-5963.

Xu, X., Sandwell, D. T., Tymofyeyeva, E., González-Ortega, A., & Tong, X. (2017). Tectonic and anthropogenic deformation at the Cerro Prieto geothermal step-over revealed by Sentinel-1A InSAR. IEEE Transactions on Geoscience and Remote Sensing, 55(9), 5284-5292. https://doi.org/10.1109/TGRS.2017.2704593


