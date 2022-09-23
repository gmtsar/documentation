.. index:: ! p2p_S1_TOPS_Frame.csh

*********************
p2p_S1_TOPS_Frame.csh
*********************

Synopsis
--------
**p2p_S1_TOPS_Frame.csh** *Master.SAFE Master.EOF Aligned.SAFE Aligned.EOF config.s1a.txt polarization parallel*

Description
-----------
**p2p_S1_TOPS_Frame.csh** A processing script for producing an interferogram from Sentinel-1 TOPS data.

Place the SAFE file in a directory called raw and a dem.grd file in a parallel directory called topo. 

Execute this command at the directory location above raw and topo.

During processing, F1, F2, F3 and merge folder will be generated. Final results will be placed in the merge folder, with phase.grd, corr

   EOF files    =  orbit files. One can download precise or restituted orbit files with :doc:`download_sentinel_orbits.csh` or :doc:`download_sentinel_orbits_linux.csh`

   polarization  =  vv  vh  hh or hv

   parallel      =  0-sequential   1-parallel-running F1/F2/F3 simultaneously


The file dem.grd is a dem that completely covers the SAR frame, or is larger than the SAR frame. If the dem is omitted then an interferogram will still be created, but there will not be a geocoded output. A custom dem.grd file can be made at the website: http://topex.ucsd.edu/gmtsar


Example
-------
  **p2p_S1_TOPS_Frame.csh** S1A_IW_SLC__1SDV_20150607T014936_20150607T015003_006261_00832E_3626.SAFE S1A_OPER_AUX_POEORB_OPOD_20150615T155109_V20150525T225944_20150527T005944.EOF S1A_IW_SLC__1SSV_20150526T014935_20150526T015002_006086_007E23_679A.SAFE S1A_OPER_AUX_POEORB_OPOD_20150627T155155_V20150606T225944_20150608T005944.EOF config.s1a.txt vv 1
