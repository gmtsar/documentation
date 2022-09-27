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

Required Arguments
------------------

*NumFiles2Cat* 

	Number of files to be concatenated (positive integer, Max: 100) 

*asa_file1*    

	First file to be merged (along track)

*asa_file2*    

	Second file to be merged (along track)

...          

	Additonal files to be merged (along track). Keep listing file names as needed.

*out_file*     

	Output data file name

Optional Argument
-----------------

*catAbort*   

	Flag to discontinue concatenation if non-overlaping frames are found. (0: Discontinue, 1: Continue, Default: 0)


Example
-------
 ::
	
    asa_cat  


