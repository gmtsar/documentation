.. index:: ! ALOS_pre_process_SLC

*********************
ALOS_pre_process_SLC
*********************

Synopsis
--------
**ALOS_pre_process_SLC** *imagefile* *LEDfile* [-radius RE] [-swap] [-V] [-debug] [-quiet] ...

Description
-----------
**ALOS_pre_process_SLC** creates .SLC (Single Look Complex) format data and writes out parameters in .PRM format 

Required Arguments
------------------

*imagefile*   

	ALOS Level 1.1 Single Look Complex file (CEOS format):

*LEDfile* 

	ALOS Level 1.1 LED file (CEOS leaderfile format):  


Optional Arguments
------------------

**-near**  *near_range* 

	Specify the *near_range* (m) 

**-radius**  *RE*   

	Specify the local earth radius *RE* (m) 

**-SLC_factor**  *fact*   

	Scale factor *fact* to convert float to int SLC [default 1.0] 

**-swap**    

	Do byte-swap (should be automatic) 

**-nodopp**    

	Does not calculate doppler (sets fd1 to zero!) 

**-ALOS1**    

	ALOS2 L1.1 data format 

**-ALOS2**    

	ALOS2 L1.1 data format (default)

**-LED**    

	Write GMTSAR generic LED format output and update PRM (default) 

**-noLED**    

	Do not write GMTSAR generic LED format output 

**-V**    

	Verbose write information) 

**-debug**    

	Write even more information 

**-quiet**    

	Don't write any information 

Example
-------
 ::

    ALOS_pre_process_SLC IMG-HH-ALOS2011986990-140813-HBQR1.1__A LED-ALOS2011986990-140813-HBQR1.1__A -SLC_factor 1. -rbias -70.0000 -tbias 0.068759 
