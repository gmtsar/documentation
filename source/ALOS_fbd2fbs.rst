.. index:: ! ALOS_fbd2fbs

************
ALOS_fbd2fbs
************

Synopsis
--------
**ALOS_fbd2fbs** *input.PRM output.PRM*

Description
-----------
**ALOS_fbd2fbs** reads in Fine Beam Double (FBD) polarization mode raw data (16MHz range sampling) 
and upsample the data in range to match Fine Beam Single (FBS) polarization mode raw data (32MHz range sampling). 
The algorithm is to read in each line of raw data, Fourier transform the data, add equal length of zeros to the end, 
and then Fourier transform back. This will keep the data feature in Frequency domain.

Example
-------
 ::

    ALOS_fbd2fbs IMG-HH-ALPSRP049040660-H1.0__A.PRM IMG-HH-ALPSRP049040660-H1.0__A_FBS.PRM
