.. index:: ! fitoffset.csh        

*************     
fitoffset.csh     
*************     

Synopsis
--------
**fitoffset.csh** *npar_rng npar_azi xcorr.dat [SNR]*


Description
-----------
**fitoffset.csh**                       


Required Arguments
------------------
    
*npar_rng*      

	Number of parameters to fit in range 

*npar_aiz*      

	Number of parameters to fit in azimuth 

*xcorr.dat*     

	Files of range and azimuth offset estimates 

Optional Argument
-----------------

*SNR*           

	Optional SNR cutoff (default 20)

Example
-------
 ::

    fitoffset.csh 3 3 freq_xcorr.dat 



