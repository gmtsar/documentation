.. index:: ! Installation

************
Installation       
************

Check out the GMTSAR github Wiki page for information about installation
via Package Manager or installing from source on Mac, Linux, or Windows 
operating systems:
 
https://github.com/gmtsar/gmtsar/wiki/GMTSAR-Wiki-Page


Are you working with ERS or Envisat Data?
-----------------------------------------

To download orbit files for ERS or Envisat satellite data visit:

 ::

        http://topex.ucsd.edu/gmtsar/tar/ORBITS.tar

Then place them in /usr/local/ and untar them:
 
 ::

        sudo -i
        cd /usr/local
        mkdir orbits
        cd orbits
        tar -xvf ~/Downloads/ORBITS.tar # (need full path to ORBITS.tar)        



