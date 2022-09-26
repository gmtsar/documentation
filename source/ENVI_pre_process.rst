.. index:: ! ENVI_pre_process

*****************
ENVI_pre_process
*****************

Synopsis
--------
**ENVI_pre_process** *<name_stem>*  *<near_range>*  *<earth_radius>* *<num_patches>* *[Doppler]*

Description
-----------
**ENVI_pre_process** will digest Envisat formatted data 


Required Arguments
------------------

*name_stem*          

	Filename of the .baq file

*near_range*         

	Near range (in meters) of the SAR image (put 0 if use default value)

*earth_radius*       

	Local earth radius (in meters) (put 0 if use default value)

*num_patch*          

	Number of patches  (put 0 if use default value)

*Doppler*            

	Doppler value (blank if use default value)

*earth_radius*       

	Local earth radius (in meters) (put 0 if use default value)



Example
-------
 ::

    ENVI_pre_process ENV1_2463_2943_15046 978992.922 6378000 5                          

This command will preprocess raw Envisat ASAR data 'ENV1_2463_2943_15046.baq'                                                 
then output parameter file 'ENV1_2463_2943_15046.PRM' and raw data file 'ENV1_2463_2943_15046.raw' 
and LED file 'ENV1_2463_2943_15046.LED'  with near range close to 978992.922 meters and 
earth radius 6378000 meters and 5 patches
