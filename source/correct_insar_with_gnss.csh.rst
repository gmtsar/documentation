.. index:: ! correct_insar_with_gnss.csh

***************************
correct_insar_with_gnss.csh
***************************

Synopsis
--------
**correct_insar_with_gnss.csh** *master.PRM phase.grd gnsslos.rad filter_wavelength* 

Description
-----------
**correct_insar_with_gnss.csh** can be used to correct an individual interferogram with GNSS displacements or to correct an InSAR velocity field with GNSS velocities.

The user must supply the grid to be corrected, as well as the GNSS observations to correct that grid. The correction takes the GNSS observations in Line-Of-Sight (LOS) and extracts the values of those locations in the InSAR grid supplied. It then computes a residual (InSAR-GNSS), and calculates an interpolated gridusing GMT surface. This grid is then filtered using a Gaussian filter of the wavelength supplied by the user (we recommend using the average station spacing of your GNSS observations). The filtered grid is then upsampled, and subtracted from your supplied InSAR grid.

Required Arguments
------------------

*master.PRM*          

	PRM file for the master SAR image
   
*phase.grd*           

	Phase file to be corrected
   
*gnsslos.rad*         

	GNSS displacements in LOS in millimeters. See :doc:`gnss_enu2los.csh` for converting GNSS ENU displacement to LOS
   
*filter_wavelength*   

	Wavelength of the filter in meters (0.5 gain)


Example
-------
 ::

    correct_insar_with_gnss.csh supermaster.PRM unwrap_dsamp.grd gnss_los.rad 40000

References
----------

The GNSS-correction/GNSS-integration method is an area of active research. To learn about the method and it's evolution,
check out these references:

Argus, D.F., Heflin, M.B., Peltzer, G., Crampé, F., & Webb, F. (2005). Interseismic strain accumulation and anthropogenic motion in metropolitan Los Angeles. Journal of Geophysical Research, 110(B04401), https://doi.org/10.1029/2003JB002934 

Guns, K., Xu, X., Bock, Y., & Sandwell, D. (2022). GNSS-corrected InSAR displacement time-series spanning the 2019 Ridgecrest, CA earthquakes. Geophysical Journal International Gravity, Geodesy, and Tides, 230, 1358-1373, https://doi.org/10.1093/gji/ggac121 

Klein, E., Bock, Y., Xu, X., Sandwell, D.T., Golriz, D., Fang, P., & Su, L. (2019). Transient Deformation in California From Two Decades of GPS Displacements: Implications for a Three-Dimensional Kinematic Reference Frame, Journal of Geophysical Research: Solid Earth, 124, https://doi.org/10.1029/2018JB017201

Neely, W.R., Borsa, A.A., & Silverii, F. (2020). GInSAR: A cGPS Correction for Enhanced InSAR Time Series, IEEE Transactions on Geoscience and Remote Sensing, 58(1), https://doi.org/10.1109/TGRS.2019.2934118

Xu, X., Sandwell, D.T., Klein, E., and Bock, Y. (2021). Integrated Sentinel-1 InSAR and GNSS Time-Series Along the San Andreas Fault System. Journal of Geophysical Research: Solid Earth, 126, https://doi.org/10.1029/2021JB022579


