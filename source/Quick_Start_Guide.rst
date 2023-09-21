.. index:: ! Quick_Start_Guide 

*****************
Quick Start Guide       
*****************

This guide is meant as a starting place for using GMTSAR software to 
process a single interferogram. There are four steps needed to set up
and run GMTSAR:

  * (1) Set up working directory
  * (2) Download SAR Data
  * (3) Download Supporting Data
  * (4) Run p2p_processing 

To see a detailed step-by-step preparation for Sentinel-1 data, check out
our Jupyter notebook:
 
  * https://github.com/gmtsar/2022-unavco-course-gmtsar/blob/main/Jupyter/gmtsar_download_prep_sentinel-1_data.ipynb

Step 1: Set Up Working Directory
--------------------------------

To ensure all files are in their proper locations, we need a specific directory
structure for processing an interferogram. In your desired location on your machine
create a top level directory with a name of your choice, such as "MyInterferogram"

 ::

   mkdir MyInterferogram/

Inside your directory, create two new directories called **topo/** and **raw/**

 ::

   cd MyInterferogram/
   mkdir topo
   mkdir raw 

Now you are ready to grab your data.

Step 2: Download SAR Data
-------------------------

To process an interferogram, you will need to download two SAR images taken at different times
and that cover the same area. These images need to be from the same track of data and the same
orbit direction (e.g., both need to be ascending or both need to be descending).

No matter what satellite data you are using, you should download the SAR data files
and place them inside the **raw/** directory inside your top level directory.

   * To choose and download Sentinel-1 L1-SLC images visit: https://search.asf.alaska.edu/#/
   * Additionally, for Sentinel-1 L1-SLC images, check out: https://scihub.copernicus.eu/dhus/#/home
   * For available data from multiple satellites check out: https://web-services.unavco.org/brokered/ssara/gui
   * *Note: You may need to make an account to download data from the above sites*

Step 3: Download Supporting Data
--------------------------------

All SAR data processing requires two primary supporting data files:

   * Orbital information (orbit files)
   * Topography information for your area (a Digital Elevation Model (DEM) file)

**Orbit Files**

For orbit files, you need the specific orbit files that correspond to each of your chosen
SAR images. Most often, you will want the "precise" orbit files for your data, as
those will contain the final orbital parameters of the satellite motion (resituted orbit files
contain the temporary/preliminary orbital parameters before they are finalized). 

   * For Sentinel-1 data, check out :doc:`download_sentinel_orbits.csh` or :doc:`download_sentinel_orbits_linux.csh`
   * For ERS or Envisat data, download the full orbits tar file: https://topex.ucsd.edu/gmtsar/downloads/

When you have your appropriate orbit files, place them in the **raw/** directory inside your top level directory.

**DEM file**

Your DEM file must cover the entire area of your SAR image (it is better to cover more area 
than necessary than to cover too little area). 

   * Check out the :doc:`Generating_DEM` page to see how to obtain DEM files 

When you have your DEM file downloaded, place the **dem.grd** file into the **topo/** directory.
 

Step 4: Run p2p_processing      
--------------------------      

Once you have your SAR data and your supporting data placed in your directory structure, you are 
ready to process your interferogram! Call the program :doc:`p2p_processing.csh` from your toplevel directory
to see its usage and inputs. To run with default parameter choices, leave the configuration_file input name 
(config.tops.txt in the following example) empty.

 ::

    p2p_processing.csh S1A_IW_SLC__1SDV_20190704T135158_20190704T135225_027968_032877_1C4D.SAFE S1A_IW_SLC__1SDV_20190716T135159_20190716T135226_028143_032DC3_512B.SAFE config.tops.txt >& log.txt &

If you want to change the default processing parameters use :doc:`pop_config.csh` to create a 
default configuration file, and edit as necessary.

    
Beyond the Wrapped Interferogram: Unwrapping
--------------------------------------------

If you are interested in also processing an unwrapped interferogram to visualize estimated
absolute displacement, you can edit the main configuration files (e.g., config.tops.txt):

   * Search for "snaphu" and find the "threshold_snaphu" parameter
   * Change this parameter from 0 to a nonzero value less than 1 to turn on unwrapping
     NOTE: do not just comment out one line and write a second line; just change the value
   * For a place to start, try threshold_snaphu = 0.1
   * Then, to run the unwrapping, change your "proc_stage" parameter to "5" at the top of your file
   * Finally, re-run p2p_processing with this edited configuration file

NOTE: the snaphu threshold value refers to a coherence threshold used for unwrapping.

If your geocoding function is turned on, you should produce a pdf and kml file of your interferogram.

Optional Presentation Choices
-----------------------------

**REFERENCE SYSTEM**: Since InSAR measurements are only with reference to the satellite, we need to 
apply a reference system to our interferograms. One way to do this is to apply a reference pixel or 
pin point in your interferogram. Another way to do this is to tie your interferogram to GNSS 
displacements. 

*Applying a Reference Point*

To apply a reference point, you need to select a pixel inside your interferogram that is a relatively
stable point (e.g., if you are calculating an earthquake interferogram, choose a point as far from the 
epicenter as possible). If you know the stable point in longitude, latitude, you can use :doc:`SAT_llt2rat`
like this to get your point in radar coordinates:

 ::
 
    SAT_llt2rat master.PRM 0 < point.llt > point.ratll 

Once you have your point in radar coordinates, you can write a short script to extract the point's value
and remove it from your entire interferogram to reference it to that point location:

 ::

    #!/bin/bash
    #
    # Applying a reference point to an interferogram
    #
    pinvalue=$( gmt grdtrack point.ratll -Gunwrap.grd | awk '{print $6}' ) 
    gmt grdmath unwrap.grd ${pinvalue} SUB = unwrap_pinned.grd
    #
    # This outputs "unwrap_pinned.grd" as a referenced interferogram

**CONVERTING RADIANS TO MILLIMETERS**: Another common presentation question is how to convert the unwrapped
interferogram in radians to the more intuitive millimeter units. You can do this with the right conversion
values like so:

 ::

    # We need to know the wavelength of the satellite you are working with
    gmt grdmath unwrap_mask.grd $wavel MUL -79.58 MUL = los_mm.grd
    
    #For Sentinel-1 data (0.0554658 is the wavelength in m)
    gmt grdmath unwrap.grd 0.0554658 MUL -79.58 MUL = unwrap_los_mm.grd

After which you can choose to plot this with GMT.

**PROJECTING INTO LAT-LON**: A last common question is how to project a grid file into geocoded
coordinates. The way to do this is to use :doc:`proj_ra2ll.csh` like this:

 ::

    #In a directory where you have a trans.dat file:
    proj_ra2ll.csh trans.dat unwrap.grd unwrap_ll.grd

    # where the third input is the specified output file name, so this command will produce the 
    # file "unwrap_ll.grd"


