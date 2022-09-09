.. index:: ! filter.csh     

**************
filter.csh
**************

Synopsis
--------
**filter.csh** *master.PRM aligned.PRM filter decimation [rng_dec azi_dec]*

Description
-----------
**filter.csh** Apply gaussian filter to amplitude and phase images.

 filter     -  wavelength of the filter in meters (0.5 gain)

 decimation - (1) better resolution, (2) smaller files 

Example
-------
**filter.csh** IMG-HH-ALPSRP055750660-H1.0__A.PRM IMG-HH-ALPSRP049040660-H1.0__A.PRM 300  2
