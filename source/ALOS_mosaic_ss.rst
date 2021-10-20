.. index:: ! ALOS_mosaic_ss

*************************
ALOS_mosaic_ss[_2frames]
*************************

Synopsis
--------
**ALOS_mosaic_ss[_2frames]** *prm1* *grd1* *prm2* *grd2* *prm3* *grd3* *prm4* *grd4* *prm5* *grd5* *mosaic* *dec* *dir* 

Description
-----------
**ALOS_mosaic_ss[_2frames]** will mosiac 5 subswath of [2 frames of] ALOS-1 ScanSAR in radar coordinates.

 prm[1-5]   -   the PRM files 
 
 grd[1-5]   -   the GMT grid files (corr, phase, phasefilt) 

 dec    -   decimation factor in radar coordinates (e.g. 10) 

 dir    -   dir is 1 means mosaic 5 subswaths, dir is 0 means divide the mosaic into 5 subswaths 

Example
-------
    **ALOS_mosaic_ss[_2frames]** 
