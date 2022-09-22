.. index:: ! p2p_S1_TOPS.csh

**************
p2p_S1_TOPS.csh
**************

Synopsis
--------
**p2p_S1_TOPS.csh** *er_stem aligned_stem configuration_file*

Description
-----------
**p2p_S1_TOPS.csh**  processing script for producing an interferogram from Sentinel-1 TOPS data 

Place the preprocessed raw data in a directory called `raw` and a `dem.grd` file in a parallel directory called `topo`. The raw data should have 4 files: two with a suffix of .dat and two with a suffix of .ldr.

Execute this command at the directory location above `raw` and `topo`.

The file `dem.grd` is a dem that completely covers the SAR frame, or is larger than the SAR frame. If the dem is omitted then an interferogram will still be created, but there will not be a geocoded output. A custom `dem.grd` file can be made at the website: http://topex.ucsd.edu/gmtsar


Reference: Xu, X., Sandwell, D.T., Tymofyeyeva, E., González-Ortega, A. and Tong, X., 
2017. Tectonic and Anthropogenic Deformation at the Cerro Prieto Geothermal 
Step-Over Revealed by Sentinel-1A InSAR. IEEE Transactions on Geoscience and 
Remote Sensing. https://doi.org/10.1109/TGRS.2017.2704593

Example
-------
  **p2p_S1_TOPS.csh** S1_20150526_F1 S1_20150607_F1 config.tsx.slc.txt  
