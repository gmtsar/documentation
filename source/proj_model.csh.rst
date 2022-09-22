.. index:: ! proj_model.csh 

**************
proj_model.csh
**************

Synopsis
--------
**proj_model.csh** *SAT ve.grd vn.grd vu.grd master.PRM dem.grd los.grd* 

Description
-----------
**proj_model.csh** project a simulated crust motion model into radar look directions (the radar look direction is spatial variable) 

  SAT             --  can be ALOS or ERS or ENVI or generic SAT

  ve, vn, vu.grd  --  input: east, north, vertical motion simulated from numerical model 

  master.PRM      --  PRM file of the radar image

  dem.grd         --  DEM grid (wider than the coverage of the radar image)

  los.grd         --  output: file name of the LOS grid 

  note that the grid of the grd files must be consistent
  note the program need master.PRM and its LED file


Example
-------
  **proj_model.csh** SAT ve.grd vn.grd vu.grd supermaster.PRM dem.grd output_los.grd  
