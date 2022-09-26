.. index:: ! ALOS_merge

**********
ALOS_merge
**********

Synopsis
--------
**ALOS_merge** *file1.PRM* *file2.PRM* [-output outfile] [-V] [-nodopp]

Description
-----------
**ALOS_merge** combines sequential ALOS-1 raw images into a single ALOS-1 raw image.
The program will append file2 onto file1 (omitting duplicate lines), updates num_lines 
and doppler (average) in PRM file output named **merge.raw** by default. If *outfile* is 
specified, the program will creates **outfile.raw** and **outfile.PRM**

Required Arguments
------------------

*file1.PRM*

	First parameter (PRM) file 

*file2.PRM*

	Second parameter (PRM) file (the file to be appended)

Optional Arguments
------------------

**-output**  *outputfile* 

	If specified, the program will create *outfile.raw* and *outfile.PRM* files.

**-V** 

	Turn on verbose mode for program screen output

**-nodopp**

	Do not calculate doppler (default is to calculate the doppler)
 

Example
-------
 ::

    ALOS_merge IMG-HH-ALPSRP057130830-H1.0__A.PRM IMG-HH-ALPSRP057130840-H1.0__A.PRM -output foo -V
