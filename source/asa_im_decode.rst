.. index:: ! asa_im_decode

*************
asa_im_decode
*************

Synopsis
--------
**asa_im_decode** *<asa_im> <asa_ins> <out> <outType> <near_range>*                


Description
-----------
**asa_im_decode** Decodes Envisat ASAR Image Mode Level 0 data.              

*asa_im_decode v1.1 by smb* 


Required Arguments
------------------

*asa_im*      

	Input image file(s) (multiple files if merging along-track)

*asa_ins*     

	Input auxilary instrument characterization data file

*out*         

	Output raw data file. **out** is a complex file with no headers (byte/float I1, byte/float Q1, byte/float I2, byte/float Q2, ...)

*outType*     

	Output file type (1=byte,4=float). If outType is byte, then the decoded floats are multiplied by 127.5, shifted by 127.5, rounded to the nearest integer and limited to the range 0-255.

*near_range*  

	Near range to which to align all lines (0=use first line near range)

Notes
-----

Starting range computed as (rank*pri+windowStartTime)*c/2 where rank is the number of pri between transmitted pulse and return echo

Calibration/noise lines are replaced with previous echo data line

Missing lines within a data set and between adjacent along-track data sets are filled with zeroes in float mode and 0.*127.5+127.5 + .5 = 128 for byte mode

Auxilary data files can be found at http://envisat.esa.int/services/auxiliary_data/asar/

Envisat ASAR Product Handbook, Issue 1.1, 1 December 2002 can be found at http://envisat.esa.int/dataproducts/asar/CNTR6-3-6.htm#eph.asar.asardf.0pASA_IM__0P


Example
-------
 ::

    asa_im_decode


