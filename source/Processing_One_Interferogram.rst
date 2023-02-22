.. index:: ! Processing_One_Interferogram

****************************
Processing One Interferogram             
****************************

What do I need to process an interferogram?
-------------------------------------------

*Input SAR Data*
        To process an interferogram you need to download two SAR images from the
        same satellite, same satellite track, and that overlap in space

*Input Orbit Files*
        You will need to provide the orbital information for each of the SAR images
        you wish to process. This information is usually available from the same place
        you downloaded data. You will need one orbit file for each image.
        
        For Sentinel-1 Orbit files (precise or restituted) check out the tool :doc:`download_sentinel_orbits.csh` or :doc:`download_sentinel_orbits_linux.csh`

*Digital Elevation Model data*
        You will need a digital elevation model (DEM) that covers the spatial extent of your SAR images.
        You can visit this website to generate one: https://topex.ucsd.edu/gmtsar/demgen/


What tool can I use to process my interferogram?
------------------------------------------------

**p2p_processing.csh**

This tool ingests multiples kinds of SAR satellite data, all with the same set up. The user must specify
the satellite type, provide the raw data and orbit files, and supply the DEM file.

Check out the :doc:`p2p_processing.csh` page to read more.

How can I set up my processing?
-------------------------------

To use :doc:`p2p_processing.csh` you need to set up a directory structure. Let's walk through a step by step guide.

 ::

    mkdir MyInterferogram  
    cd MyInterferogram
    mkdir raw
    mkdir topo

Move your DEM file into topo/ and change its name to dem.grd
Move your two SAR images and their two respective orbit files into raw/
From the directory MyInterferogram, run the :doc:`p2p_processing.csh` command.

 ::

    p2p_processing.csh ALOS IMG-HH-ALPSRP055750660-H1.0__A IMG-HH-ALPSRP049040660-H1.0__A config.alos.txt >& p2p_process_feb22.log &
    
Always save your command to a log file. This makes it much easier to debug if something goes awry.

You can follow your log file with the tail command, for example

 ::

    tail -f p2p_process_feb22.log 


How do I change the default processing settings?
------------------------------------------------

The :doc:`p2p_processing.csh` command creates a default config.txt file for the given satellite. 
This configuration file uses only default values for all interferogram processing, such as a default
filter wavelength, decimation size, and a default assumption not to unwrap the interferogram.

To change these and any other settings, create a new config.txt file with
the tool :doc:`pop_config.csh` and edit your configuration file as desired.

Common setting questions:

*How do I turn on unwrapping?*  Change the threshold_snaphu value to a nonzero value (try 0.1)

*I turned on unwrapping and the coherence threshold is too small! How do I change it?* Change the threshold_snaphu value to a larger value. This is the threshold of coherence for accepting and processing pixels in your interferogram. 

*I don't want all the geocoded products right now. How do I turn it off?* Change threshold_geocode to zero

*For the region cut, how do I choose what values to use?* It's written in minrange/maxrange/minazimuth/maxazimuth. You can check out one of your corr.pdf phase.pdf or phasefilt.pdf files to determine what area you want to isolate.



