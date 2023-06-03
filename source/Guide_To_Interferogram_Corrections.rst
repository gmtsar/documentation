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
(the Generic Atmospheric Correction Online Service correction) (Yu et al., 2017,2018a,2018b). You can download
a GACOS correction grid and read more about the process here: http://www.gacos.net/

The accuracy and benefit of this particular correction will vary depending on your study area. We make
no guarantees that this will remove all of your tropospheric noise, but it may help.

Citations for GACOS:

Yu, C., Li, Z., Penna, N. T., & Crippa, P. (2018). Generic atmospheric correction model for Interferometric Synthetic 
Aperture Radar observations. Journal of Geophysical Research: Solid Earth, 123(10), 9202-9222

Yu, C., Li, Z., & Penna, N. T. (2018). Interferometric synthetic aperture radar atmospheric correction using a GPS-based 
iterative tropospheric decomposition model. Remote Sensing of Environment, 204, 109-121

Yu, C., Penna, N. T., & Li, Z. (2017). Generation of real‐time mode high‐resolution water vapor fields from GPS observations. 
Journal of Geophysical Research: Atmospheres, 122(3), 2008-2025 

GNSS Correction
---------------

Check out :doc:`correct_insar_with_gnss.csh` to read more about this.

*Page in progress*


