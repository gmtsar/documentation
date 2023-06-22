.. index:: ! Guide_To_Interferogram_Corrections

**********************************
Guide To Interferogram Corrections
**********************************

There are many ways to apply different corrections to interferograms. This is **not** an
exhaustive list in any way. Many of these correction topics are active areas of research, but
we list these here in case they might help.

Atmospheric Corrections
-----------------------

The atmosphere can be a large source of noise in SAR interferograms, especially because any signal 
delay gets doubled because the radar signal has to pass through the atmosphere to get to the ground
and then back through the atmosphere when it is reflected. Correcting these delay effects is an active
area of research, but one main area is in correcting the tropospheric delay which can be accomplished
by using Weather Models or by using Global Navigation Satellite System (GNSS) point-based Zenith 
Tropospheric Delay (ZTD) measurements.  

*Tropospheric Delay with GACOS*

One straightforward way to try to correct for tropospheric delay is to apply the GACOS Correction
(the Generic Atmospheric Correction Online Service correction) which is currently based on 
weather model data for global grids (see Yu et al., 2017,2018a,2018b). You can download
a GACOS correction grid and read more about the process here: http://www.gacos.net/

The accuracy and benefit of this particular correction will vary depending on your study area. We make
no guarantees that this will remove all of the tropospheric noise in your study area, but it may help.

A script exists for using GMTSAR to incorporate GACOS grids; see github at:
https://github.com/gmtsar/user-contributions/tree/main/gacos-correction 


Citations for GACOS:

Yu, C., Li, Z., Penna, N. T., & Crippa, P. (2018). Generic atmospheric correction model for Interferometric Synthetic 
Aperture Radar observations. Journal of Geophysical Research: Solid Earth, 123(10), 9202-9222

Yu, C., Li, Z., & Penna, N. T. (2018). Interferometric synthetic aperture radar atmospheric correction using a GPS-based 
iterative tropospheric decomposition model. Remote Sensing of Environment, 204, 109-121

Yu, C., Penna, N. T., & Li, Z. (2017). Generation of real‐time mode high‐resolution water vapor fields from GPS observations. 
Journal of Geophysical Research: Atmospheres, 122(3), 2008-2025 

GNSS Correction/Integration
---------------------------

With the recent July 2021 GMTSAR distribution we have included a new script called correct_insar_with_gnss.csh
which allows you to use your own GNSS displacements to correct InSAR interferograms for additional atmospheric
effects. This also ties your interferogram to GNSS motions and helps provide an underlying reference frame. 
This script uses the general approach of Neely et al. (2020) (e.g. GInSAR), but instead of solving for a best-fit 
residual correction grid, this script applies a Gaussian filter to the correction grid before removing it from
the interferogram. This approach is documented in Klein et al. (2019) and most recently by Xu et al. (2021) and 
Guns et al. (2022). This gaussian filter is user-specified (in units of meters), and we recommend using the value
of average station spacing in your GNSS data set (in the example line below, we have an average station spacing of 
40 km, so we use 40,000 meters as our gaussian filter wavelength).

::
 
    correct_insar_with_gnss.csh supermaster.PRM unwrap_dsamp.grd gnss_los.rad 40000

Check out :doc:`correct_insar_with_gnss.csh` to read more about this.

References:

Guns, K., Xu, X., Bock, Y., Sandwell, D., 2022, GNSS-corrected InSAR displacement time-series spanning the 
2019 Ridgecrest, CA earthquakes, Geophysical Journal International, Volume 230, Issue 2, September 2022, 
Pages 1358–1373, https://doi.org/10.1093/gji/ggac121

Neely, W.R., Borsa, A.A., and Silverii, F., 2020. GInSAR: A cGPS Correction for Enhanced InSAR Time Series, 
IEEE Transactions on Geoscience and Remote Sensing, 58(1), 136 - 146, https://doi.org/10.1109/TGRS.2019.2934118. 

Klein, E., Bock, Y., Xu, X., Sandwell, D. T., Golriz, D., Fang, P., & Su, L. (2019). Transient deformation in 
California from two decades of GPS displacements: Implications for a three-dimensional kinematic reference frame. 
Journal of Geophysical Research: Solid Earth, 124, 12189– 12223. https://doi.org/10.1029/2018JB017201

Xu, X., Sandwell, D. T., Klein, E., & Bock, Y. (2021). Integrated Sentinel-1 InSAR and GNSS time-series along the 
San Andreas fault system. Journal of Geophysical Research: Solid Earth, 126, e2021JB022579. https://doi.org/10.1029/2021JB022579


*Page in progress as more research progresses*


