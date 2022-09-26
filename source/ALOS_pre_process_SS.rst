.. index:: ! ALOS_pre_process_SS

*********************
ALOS_pre_process_SS
*********************

Synopsis
--------
**ALOS_pre_process_SS** *imagefile* *LEDfile* [-radius RE] [-swath swath#] [-burst_skip] 
[-num_burst] [-swap] [-V] [-debug] [-quiet] ...

Description
-----------
**ALOS_pre_process_SS** creates .raw format data and writes out parameters in .PRM format 


Required Arguments
------------------

*imagefile*   

	ALOS Level 1.0 complex ScanSAR file (CEOS format):

*LEDfile*    

	ALOS Level 1.0 LED file (CEOS leaderfile format):  


Optional Arguments
------------------

**-near**  *near_range*   

	Specify the *near_range* (m) 

**-radius**  *RE*   

	Specify the local earth radius *RE* (m) 

**-SLC_factor**  *fact*   

	Scale factor *fact* to convert float to int SLC [default 1.0] 

**-swath**  *N*   

	Specify swath number *N* 1-5 [default 4] 

**-burst_skip**  *M*   

	Number of burst *M* to skip before starting output (1559 lines/burst) 

**-num_burst**  *N_burst*   

	Number of burst *N_burst* to process [default all] (there are 72 bursts in a WB1 frame) 

**-swap**    

	Do byte-swap (should be automatic) 

**-fd1**  *DOPP*   

	Sets doppler centroid [fd1] to *DOPP*

**-V**   

	Verbose write information) 

**-debug**   

	Write even more information 

**-quiet**    

	Don't write any information 
        
Example
-------
 ::

    ALOS_pre_process_SS IMG-HH-ALPSRS049842950-W1.0__D LED-ALPSRS049842950-W1.0__D -near 847916 -radius 6371668.872945 -burst_skip 5 -num_burst 36 
