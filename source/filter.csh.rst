.. index:: ! filter.csh     

**********
filter.csh
**********

Synopsis
--------
**filter.csh** *master.PRM aligned.PRM filter decimation [rng_dec azi_dec]*

Description
-----------
**filter.csh** Apply gaussian filter to amplitude and phase images.

Required Arguments
------------------

*master.PRM*

	Parameter file for the master or reference image

*aligned.PRM*

	Parameter file for the aligned or secondary image

*filter*

	Wavelength of the filter in meters (0.5 gain)

*decimation*

	(1) better resolution or (2) smaller files

Optional Arguments
------------------

*rng_dec* and *azi_dec*

	Decimation factors desired for range (rng) and azimuth (azi)


Example
-------
 ::

    filter.csh IMG-HH-ALPSRP055750660-H1.0__A.PRM IMG-HH-ALPSRP049040660-H1.0__A.PRM 300  2
