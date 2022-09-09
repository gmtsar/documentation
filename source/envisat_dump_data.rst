.. index:: ! envisat_dump_data    

************      
envisat_dump_data 
************      

Synopsis
--------
**envisat_dump_data**  *envisat-product outputfile [l0 lN p0 pN]*


Description
-----------
**envisat_dump_data**                
    
        envisat-product is the input filename
        outputfile      is the output filename
        l0              is the first azimuth line (starting at 1)
        lN              is the last azimuth line
        p0              is the first range pixel (starting at 1)
        pN              is the last range pixel


Example
-------
    **envisat_dump_data** ASA_IMS_1PNDPA20021025_175208_000000162010_00356_03416_0005.N1 crop.out 0 10 0 100



