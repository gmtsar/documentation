.. index:: ! ALOS_pre_process

*****************
ALOS_pre_process
*****************

Synopsis
--------
**ALOS_pre_process** *imagefile* *LEDfile* [-near near_range] [-radius RE] [-swap] [-V] [-debug] [-quiet] ...

Description
-----------
**ALOS_pre_process** creates .raw format data and writes out parameters in .PRM format 

Required Arguments
------------------

*imagefile*   

	ALOS Level 1.0 complex file (CEOS format):

*LEDfile* 

	ALOS Level 1.0 LED file (CEOS leaderfile format):  

Optional Arguments
------------------

**-near**  *near_range* 

	Specify the *near_range* (m) 

**-radius**  *RE* 

	Specify the local earth radius *RE* (m) 

**-swap**  

	Do byte-swap (should be automatic) 

**-nodopp**  

	Does not calculate doppler (sets fd1 to zero!) 

**-npatch**  

	Set the number of patches 

**-fd1**  *DOPP*  

	Sets doppler centroid [fd1] to *DOPP*

**-quad** 

	Adjust parameters for quad pol mod (PRF/2)

**-ALOSE**  

	Use ERSDAC format 

**-ALOS**  

	Use AUIG format (default) 

**-LED**  

	Write GMTSAR generic LED format output and update PRM (default) 

**-noLED**  

	Do not write GMTSAR generic LED format output 

**-roi**  

	Write roi_pac format output

**-V**  

	Verbose write information) 

**-debug**  

	Write even more information 

**-quiet**  

	Don't write any information 

**-force_slope**  *chirp_slope* 

	Force a value for the *chirp_slope*

**-chirp_ext**  *chirp_ext* 

	Force a value for the chirp extension *chirp_ext* (integer)

**-tbias**  *tbias* 

	Correct the clock bias *tbias* (positive value means plus)

Example
-------
 ::

    ALOS_pre_process  IMG-HH-ALPSRP050420840-H1.0__A  LED-ALPSRP050420840-H1.0__A  
