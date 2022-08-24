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
**ALOS_baseline** creates a baseline table using mode 1 (two input fils) or mode 2 (one input file)
Mode 1:
ALOS_baseline can be used to generate baseline parameters for one pair of images.
This mode requires the input master PRM file name and the secondary or aligned PRM file name and
parameters will be written for appending to a PRM file.

Mode 2:
ALOS_Baseline can be used to generate baseline parameters for a list of images, with the firs
image in the list assumed to be the master image, and all others listed to be the secondary aligned
images. This writes out decimal year, perpendicular baseline, and the PRM name.

Example
-------
    **ALOS_baseline** IMG-HH-ALPSRP049040660-H1.0__A.PRM IMG-HH-ALPSRP049050660-H1.0__A.PRM

or

    **ALOS_baseline** PRM.list 
