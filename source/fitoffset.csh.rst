.. index:: ! fitoffset.csh        

************      
fitoffset.csh     
************      

Synopsis
--------
**fitoffset.csh** *npar_rng npar_azi xcorr.dat [SNR]*


Description
-----------
**fitoffset.csh**                       
    
        npar_rng    - number of parameters to fit in range 

        npar_aiz    - number of parameters to fit in azimuth 

        xcorr.dat   - files of range and azimuth offset estimates 

        SNR         - optional SNR cutoff (default 20)

Example
-------
    **fitoffset.csh** 3 3 freq_xcorr.dat 



