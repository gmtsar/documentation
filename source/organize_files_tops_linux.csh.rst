.. index:: ! organize_files_tops_linux.csh

*****************************
organize_files_tops_linux.csh
*****************************

Synopsis
--------
**organize_files_tops_linux.csh** *filelist pins.ll mode*

Description
-----------
**organize_files_tops_linux.csh** organize one track of S1A TOPS data, redefine frames, auto-download precise orbits on a linux machine; if restituted orbits are required, user must download separately 

To download restituted orbit files for Sentinel-1 data, use :doc:`download_sentinel_orbits.csh` or :doc:`download_sentinel_orbits_linux.csh` 

Required Arguments
------------------

*filelist*

	List of SAFE files to be stitched, with absolute path, in time order

*pins.ll*

	List of stitching locations. Each list must have a minimum of two pins, but if you are attempting to stitch multiple frames that span over ~150 km, additional pins should be added in between your start and end pin points. Additionally, maximum stitching distance is currently ~500 km (stitching frames longer than this distance may introduce issues into interferogram processing).

	Format of pins.ll file (point 1 and point2 must be listed with first point in orbit direction first, e.g., descending orbit should have the northernmost point before the southernmost point):

		lon1 lat1

		lon2 lat2

		...

*Mode*

	Processing mode. Mode = 1 will tell how many records are going to be generated. mode = 2 will do the organizing and stitching (mode 2 takes a longer processing time).


Example
-------
 ::

    organize_files_tops_linux.csh SAFEfile.list T035_pins.ll 1 
