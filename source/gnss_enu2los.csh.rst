.. index:: ! gnss_enu2los.csh

**************
gnss_enu2los.csh
**************

Synopsis
--------
**gnss_enu2los.csh** *master.PRM master.LED gnss.sllenu dem.grd*

Description
-----------
**gnss_enu2los.csh** will convert given east/north/up GNSS observations to Line-Of-Sight (LOS) displacements 

   master.PRM        -  PRM file for the master SAR image
  
   master.LED*       -  LED file for the master SAR image
  
   gnss.llenu**      -  GNSS displacements (Stat | Lon | Lat | E | N | U) in millimeters
  
   dem.grd           -  DEM grid file from your insar processing
 
Note: Ensure you have the correct LED files listed in the master.PRM file -- they must match 
 
Assumes the gnss.llenu file is a list of stations with a specific displacement value (e.g. the displacement between two insar scenes, or the velocity of a single point) per station.
 
Check out :doc:`correct_insar_with_gnss.csh` to correct your interferogram (or InSAR velocity field) with GNSS data

Example
-------
   **gnss_enu2los.csh**  master.PRM master.LED gnss_2019-2018.sllenu dem.grd 
