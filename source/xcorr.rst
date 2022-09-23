.. index:: ! xcorr                

************      
xcorr             
************      

Synopsis
--------
**xcorr**  *master.PRM aligned.PRM [-time] [-real] [-freq] [-nx n] [-ny n] [-xsearch xs] [-ysearch ys]*


Description
-----------
**xcorr** Compute 2-D cross-correlation of two images            


Input:
    
  master.PRM     	PRM file for reference image
  
  aligned.PRM     	 	PRM file of secondary image
  
  -time      		use time cross-correlation
  
  -freq      		use frequency cross-correlation (default)
  
  -real      		read float numbers instead of complex numbers
  
  -noshift  		ignore ashift and rshift in prm file (set to 0)
  
  -nx  nx    		number of locations in x (range) direction (int)
  
  -ny  ny    		number of locations in y (azimuth) direction (int)
  
  -nointerp     		do not interpolate correlation function
  
  -range_interp ri  	interpolate range by ri (power of two) [default: 2]
  
  -norange     		do not range interpolate 
  
  -xsearch xs		search window size in x (range) direction (int power of 2 [32 64 128 256])
  
  -ysearch ys		search window size in y (azimuth) direction (int power of 2 [32 64 128 256])
  
  -interp  factor    	interpolate correlation function by factor (int) [default, 16]
  
  -v			verbose


Output: 

  freq_xcorr.dat (default) 

  time_xcorr.dat (if -time option))


use :doc:`fitoffset.csh` to convert output to PRM format


Example
-------
    **xcorr** IMG-HH-ALPSRP075880660-H1.0__A.PRM IMG-HH-ALPSRP129560660-H1.0__A.PRM -nx 20 -ny 50 

or

    **xcorr** file1.grd file2.grd -nx 20 -ny 50 (takes grids with real numbers)


