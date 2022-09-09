.. index:: ! conv                 

************      
conv          
************      

Synopsis
--------
**conv**  *idec jdec filter_file input output*


Description
-----------
**conv** 2-D image convolution                                  
    
   idec           - row decimation factor 

   jdec           - column decimation factor 

   filter_file    - eg. filters/gauss17x5 

   input          - name of file to be filtered (I*2 or R*4) 

   output         - name of filtered output file (R*4 only) 

Examples
-------
    **conv** 4 2 filters/gauss9x5 IMG-HH-ALPSRP109430660-H1.0__A.PRM test.grd

       (makes and filters amplitude file from an SLC-file)


    **conv** 4 2 filters/gauss5x5 infile.grd outfile.grd 
   
       (filters a float file) 
 



