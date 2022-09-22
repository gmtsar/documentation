.. index:: ! pre_proc_init.csh 

**************
pre_proc_init.csh 
**************

Synopsis
--------
**pre_proc_init.csh** *SAT data.in* 

Description
-----------
**pre_proc_init.csh** Preprocess a set of images using default Doppler centroid, rear_range and radius, number of patches.

This will generate a baseline-time plot, and after running this command, a user should choose an appropriate master/reference image.

The user should also decide a common Doppler centroid, rear_range and radius, number of patches to run batch processing. The data with completely different Doppler centroid or baselines can be omitted from further processing.  

 SAT can be ALOS ERS or ENVI(ENVISAT)      

       format of data.in is:
 
         line 1: master_name 
 
         line 2 and below: aligned_name


       example of data.in for ALOS is:
 
         IMG-HH-ALPSRP096010650-H1.0__A
 
         IMG-HH-ALPSRP089300650-H1.0__A
 
         IMG-HH-ALPSRP236920650-H1.0__A


       example of data.in for ERS is:
  
         e1_05783
 
         e1_07787
 
         e1_10292


       example of data.in for ENVISAT is:
 
         ENV1_2_127_2925_07195
 
         ENV1_2_127_2925_12706
 
         ENV1_2_127_2925_13207

 

Example
-------
  **pre_proc_init.csh** ENVI data.in 
