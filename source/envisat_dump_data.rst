.. index:: ! envisat_dump_data    

*****************      
envisat_dump_data 
*****************      

Synopsis
--------
**envisat_dump_data**  *envisat-product outputfile [l0 lN p0 pN]*


Description
-----------
**envisat_dump_data**                

Required Arguments
------------------
    
*envisat-product* 

	The input filename   

*outputfile*      

	The output filename

Optional Arguments
------------------

*l0*              

	Is the first azimuth line (starting at 1)

*lN*              

	Is the last azimuth line

*p0*              

	Is the first range pixel (starting at 1)

*pN*              

	Is the last range pixel


Example
-------
 ::

    envisat_dump_data ASA_IMS_1PNDPA20021025_175208_000000162010_00356_03416_0005.N1 crop.out 0 10 0 100



