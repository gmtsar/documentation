.. index:: ! p2p_ENVI.csh   

**************
p2p_ENVI.csh  
**************

Synopsis
--------
**p2p_ENVI.csh** *master_stem aligned_stem configuration_file*

Description
-----------
**p2p_ENVI.csh** is a processing script for producing an interferogram from ENVISAT data 

Place the raw data in a directory called `raw` and a `dem.grd` file in a parallel directory called `topo`. The two files of raw data must have a suffix .baq

Execute this command at the directory location above `raw` and `topo`.

The file `dem.grd` is a dem that completely covers the SAR frame, or is larger than the SAR frame. If the dem is omitted then an interferogram will still be created, but there will not be a geocoded output. A custom `dem.grd` file can be made at the website: http://topex.ucsd.edu/gmtsar


Example
-------
  **p2p_ENVI.csh** ENV1_2_077_0639_0657_41714 ENV1_2_077_0639_0657_42716 config.envi.txt
