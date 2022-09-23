.. index:: ! ALOS_fbd2ss

***********
ALOS_fbd2ss
***********

Synopsis
--------
**ALOS_fbd2ss** *input.PRM* *SubSwath.PRM* *ashift* *ntot* *a_stretch_a*

Description
-----------
**ALOS_fbd2ss** reads in Fine Beam Double (FBD) polarization mode raw data (16MHz range sampling) 
and convert it to match a specific subswath of ALOS ScanSAR data.

Required Arguments
------------------

*input.PRM* 
	
	PRM file for input  image in fine beam dual polarization (FBD 14 MHz) (input) 

*SubSwath.PRM* 

	PRM file with appropriate lines zeroed to match a WB1_SW4 file 

*ashift* 

	Azimuth shift needed to align the first row of the FBD to the SubSwath 

*ntot*  

	Total number of rows between bursts in the SubSwath (i.e. *num_valid_az*/6)

*a_stretch_a* 

	Either the parameter from matching or (*PRF_SubSwath* - *PRF_input*)/*PRF_input*

Example
-------
 ::

    ALOS_fbd2ss IMG-HH-ALPSRP049040660-H1.0__A.PRM IMG-HH-ALPSRP049040660-H1.0__A4.PRM -1046 1684 0.010972
