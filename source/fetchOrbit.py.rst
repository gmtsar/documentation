.. index:: ! fetchOrbit.py  

*************
fetchOrbit.py 
*************

Synopsis
--------
**fetchOrbit.py** *path_to_SAFE_file path_to_output_directory*

Description
-----------
**fetchOrbit.py** will reach out and download orbit files related to a given SAFE file

Note: Downloads Sentinel-1 satellite orbits from the Copernicus HUB

Required Arguments
------------------

*path_to_SAFE_file*

	The absolute path to the SAFE file

*path_to_output_directory*

	The path to the directory where you want your orbit files to be stored 

Example
-------
 ::

    fetchOrbit.py /InSARwork/Test/S1B_IW_SLC__1SDV_20171017T015804_20171017T015837_007863_00DE2F_8201.SAFE /InSARwork/Test/orbit_files 
