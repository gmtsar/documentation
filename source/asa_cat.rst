.. index:: ! asa_cat      

************
asa_cat      
************

Synopsis
--------
**asa_cat** *<NumFiles2Cat> <asa_file1> <asa_file2> <...>  <out_file> [catAbort]*


Description
-----------
**asa_cat** Concatenates Envisat ASAR Image Mode / Wide Swath Mode Level 0 data.             

*asa_cat v1.3 by Dochul Yang and Vikas Gudipati*

       NumFiles2Cat Number of files to be concatenated (positive integer, Max: 100) 

       asa_file1    First file to be merged (along track)

       asa_file2    Second file to be merged (along track)

       ...          Rest of files to be merged (along track)

       out_file     output data file

       [catAbort]   Flag to discontinue concatenation if non-overlaping frames are found. (0: Discontinue, 1: Continue, Default: 0)


Example
-------
    **asa_cat**  


