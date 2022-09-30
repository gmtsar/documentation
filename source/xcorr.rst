.. index:: ! xcorr                

*****      
xcorr             
*****      

Synopsis
--------
**xcorr**  *master.PRM aligned.PRM [-time] [-real] [-freq] [-nx n] [-ny n] [-xsearch xs] [-ysearch ys]*


Description
-----------
**xcorr** Compute 2-D cross-correlation of two images            

Outputs:

  freq_xcorr.dat (default) 

  time_xcorr.dat (if -time option))


Use :doc:`fitoffset.csh` to convert output to PRM format

Required Arguments
------------------
    
*master.PRM*     	

	PRM file for reference image
  
*aligned.PRM*     	 	

	PRM file of secondary image

Optional Arguments
------------------
  
**-time**      		

	Use time cross-correlation
  
**-freq**      		

	Use frequency cross-correlation (default)
  
**-real**      		

	Read float numbers instead of complex numbers
  
**-noshift**  		

	Ignore ashift and rshift in prm file (set to 0)
  
**-nx**  *nx*    		

	Number of locations in x (range) direction (int)
  
**-ny**  *ny*    		

	Number of locations in y (azimuth) direction (int)
  
**-nointerp**     		

	Do not interpolate correlation function
  
**-range_interp** *ri*  	

	Interpolate range by ri (power of two) [default: 2]
  
**-norange**     		

	Do not range interpolate 
  
**-xsearch** *xs*		

	Search window size in x (range) direction (int power of 2 [32 64 128 256])
  
**-ysearch** *ys*		

	Search window size in y (azimuth) direction (int power of 2 [32 64 128 256])
  
**-interp**  *factor*    	

	Interpolate correlation function by factor (int) [default, 16]
  
**-v**			

	Verbose


Example
-------
 ::

    xcorr IMG-HH-ALPSRP075880660-H1.0__A.PRM IMG-HH-ALPSRP129560660-H1.0__A.PRM -nx 20 -ny 50 

or

 ::

    xcorr file1.grd file2.grd -nx 20 -ny 50 

(takes grids with real numbers)


