.. index:: ! ERS_pre_process 

*****************
ERS_pre_process 
*****************

Synopsis
--------
**ERS_pre_process** *<name_stem>*  *<near_range>*  *<earth_radius>* *<num_patches>* *[Doppler]*

Description
-----------
**ERS_pre_process** will digest ERS SAR data           

     name_stem     -    filename of the .dat and .ldr file
 
     near_range    -    near range (in meters) of the SAR image (put 0 if use default value)

     earth_radius  -    local earth radius (in meters) (put 0 if use default value)
 
     num_patch     -    number of patches  (put 0 if use default value)
 
     Doppler       -    Doppler value (blank if use default value)


Example
-------
    **ERS_pre_process** ERS_pre_process ERS2_356_2925_61332 978992.922 6378000 5           

This command will preprocess ERS2 SAR data 'ERS2_356_2925_61332'                                                              
then output parameter file 'ERS2_356_2925_61332.PRM' and fixed raw data                           
file 'ERS2_356_2925_61332.raw' and LED file ERS2_356_2925_61332.LED
with near range close to 978992.922 meters and earth radius 6378000 meters and 5 patches 
