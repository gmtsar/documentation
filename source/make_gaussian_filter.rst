.. index:: ! make_gaussian_filter

********************
make_gaussian_filter
********************

Synopsis
--------
**make_gaussian_filter** *name_of_PRM_file RNG_DEC AZI_DEC WAVELENGTH(m)*

Description
-----------
**make_gaussian_filter** creates a gaussian filter of specified wavelength  

Outputs a file called gauss_NNN, where NNN is your filter wavelength (e.g. if you choose a wavelength of 200 m, your output file will be called **gauss_200** )

Required Arguments
------------------

*name_of_PRM_file*

	Parameter (PRM) file name

*RNG_DEC*

	Decimation in range direction

*AZI_DEC*

	Decimation in azimuth direction

*WAVELENGTH*
	
	Wavelength in meters

Example
-------
 ::

    make_gaussian_filter IMG-HH-ALPSRP211830620-H1.0__A.PRM 2 4 200           

