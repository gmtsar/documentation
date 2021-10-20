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

    imagefile   -   ALOS Level 1.0 complex file (CEOS format):

    LEDfile -   ALOS Level 1.0 LED file (CEOS leaderfile format):  

    options: 

        -near *near_range* - specify the *near_range* (m) 

        -radius *RE* - specify the local earth radius *RE* (m) 

        -swap - do byte-swap (should be automatic) 

        -nodopp - does not calculate doppler (sets fd1 to zero!) 

        -npatch - set the number of patches 

        -fd1 *DOPP* : sets doppler centroid [fd1] to *DOPP*

        -quad - adjust parameters for quad pol mod (PRF/2)

        -ALOSE - use ERSDAC format 

        -ALOS - use AUIG format (default) 

        -LED - write GMTSAR generic LED format output and update PRM (default) 

        -noLED - do not write GMTSAR generic LED format output 

        -roi - write roi_pac format output

        -V - verbose write information) 

        -debug - write even more information 

        -quiet - don't write any information 

        -force_slope *chirp_slope* - force a value for the *chirp_slope*

        -chirp_ext *chirp_ext* - force a value for the chirp extension *chirp_ext* (integer)

        -tbias *tbias* - correct the clock bias *tbias* (positive value means plus)

Example
-------
    **ALOS_pre_process**  IMG-HH-ALPSRP050420840-H1.0__A  LED-ALPSRP050420840-H1.0__A  
