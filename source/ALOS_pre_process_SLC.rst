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

    imagefile   -   ALOS Level 1.1 Single Look Complex file (CEOS format):

    LEDfile -   ALOS Level 1.1 LED file (CEOS leaderfile format):  

    options: 

        -near *near_range* - specify the *near_range* (m) 

        -radius *RE* - specify the local earth radius *RE* (m) 

        -SLC_factor *fact* - scale factor *fact* to convert float to int SLC [default 1.0] 

        -swap - do byte-swap (should be automatic) 

        -nodopp - does not calculate doppler (sets fd1 to zero!) 

        -ALOS1 - ALOS2 L1.1 data format 

        -ALOS2 - ALOS2 L1.1 data format (default)

        -LED - write GMTSAR generic LED format output and update PRM (default) 

        -noLED - do not write GMTSAR generic LED format output 

        -V - verbose write information) 

        -debug - write even more information 

        -quiet - don't write any information 

Example
-------
    **ALOS_pre_process_SLC** IMG-HH-ALOS2011986990-140813-HBQR1.1__A LED-ALOS2011986990-140813-HBQR1.1__A 
    -SLC_factor 1. -rbias -70.0000 -tbias 0.068759 
