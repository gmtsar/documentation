.. index:: ! ENVI_SLC_pre_process

********************
ENVI_SLC_pre_process
********************

Synopsis
--------
**ENVI_SLC_pre_process** *<name_stem>* *<earth_radius>* 

Description
-----------
**ENVI_SLC_pre_process** will digest Envisat formatted L.1 data from the ERS-1 ERS-2 and ENVISAT platforms
(files with extension .E1 .E2 or .N1). It will not (yet) read the Wide Scan mode format
(file names starting with ASA_WSS_1P)

Required Arguments
------------------

*name_stem*    

	Filename of the data file

*earth_radius*       

	Local earth radius (in meters) (put 0 if use default value)



Example
-------
 ::

    ENVI_SLC_pre_process ASA_IMS_1PNESA20060130_054255_000000182044_00392_20486_0000 6378000

This command will preprocess Envisat formatted L.1 ASAR data 'ASA_IMS_1PNESA20060130_054255_000000182044_00392_20486_0000.N1' 
then output parameter file 'ASA_IMS_1PNESA20060130_054255_000000182044_00392_20486_0000.PRM', SLC data file 
'ASA_IMS_1PNESA20060130_054255_000000182044_00392_20486_0000.SLC' and LED file 'ASA_IMS_1PNESA20060130_054255_000000182044_00392_20486_0000.LED' with earth radius 6378000 meters
