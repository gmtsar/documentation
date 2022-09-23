.. index:: ! ALOS_baseline

************
ALOS_baseline
************

Synopsis
--------
**ALOS_baseline** *PRM_master* *PRM_aligned*

or

**ALOS_baseline** *PRM.list*

Description
-----------
**ALOS_baseline** creates a baseline table using mode 1 (two input files) or mode 2 (one input file)

Mode 1:
  ALOS_baseline can be used to generate baseline parameters for one pair of images.
  This mode requires the input master PRM file name and the secondary or aligned PRM file name and
  parameters will be written for appending to a PRM file.

Mode 2:
  ALOS_Baseline can be used to generate baseline parameters for a list of images, with the firs
  image in the list assumed to be the master image, and all others listed to be the secondary aligned
  images. This writes out decimal year, perpendicular baseline, and the PRM name.

Required Arguments
-----------
Mode 1:

*PRM_master* 
	
	Master or reference image PRM file.

*PRM_aligned*

	Aligned or secondary image PRM file.

Mode 1:

*PRM.list*

	List of image PRM files, where the first line in the file is assumed to be the master image.

Example
-------
Mode 1::     

    ALOS_baseline IMG-HH-ALPSRP049040660-H1.0__A.PRM IMG-HH-ALPSRP049050660-H1.0__A.PRM

Mode 2:: 

    ALOS_baseline PRM.list 
