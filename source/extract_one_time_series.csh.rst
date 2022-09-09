.. index:: ! extract_one_time_series.csh

**************
extract_one_time_series.csh
**************

Synopsis
--------
**extract_one_time_series.csh** *longitude latitude masterPRM dem.grd scene.tab [m_rng m_azi]*

Description
-----------
**extract_one_time_series.csh** Extracts a LOS time series from existing disp*.grd files produced by the :doc:`sbas` program

Input:

   longitude/latitude  -  point of interest

   masterPRM           -  master PRM file

   dem.grd             -  dem.grd file from processing 

   scene.tab           -  is the same input needed by :doc:`sbas`
   
   m_rng and m_azi     -  is the number of pixels to be averaged for output, default is 5 5


Output: **time_series.dat** will have two colums of data, displacements and standard deviation 

Example
-------
**extract_one_time_series.csh** -119.782 36.292 supermaster.PRM dem.grd scene.tab 5 5 
