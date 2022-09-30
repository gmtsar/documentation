.. index:: ! slc2amp.csh    

***********
slc2amp.csh   
***********

Synopsis
--------
**slc2amp.csh** *filein.PRM rng_dec fileout.grd*

Description
-----------
**slc2amp.csh** 

Required Arguments
------------------

*filein.PRM*

	Input parameter (PRM) file

*rng_dec*

	Range decimation

	e.g. 1 for ERS ENVISAT ALOS FBD

            2 for ALOS FBS 

            4 for TSX

*fileout.grd*

	Specify output name for grid file

Example
-------
 ::

    slc2amp.csh IMG-HH-ALPSRP055750660-H1.0__A.PRM 2 amp-ALPSRP055750660-H1.0__A.grd
