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

   * To download a DEM from SRTM1, SRTM3, or ASTER1 visit: https://topex.ucsd.edu/gmtsar/demgen/

When you have your DEM file downloaded, place the **dem.grd** file into the **topo/** directory.
 

Step 4: Run p2p_processing      
--------------------------      

Once you have your SAR data and your supporting data placed in your directory structure, you are 
ready to process your interferogram! Call the program :doc:`p2p_processing.csh` from your toplevel directory
to see its usage and inputs. To run with default parameter choices, leave the configuration_file input empty.

 ::

    p2p_processing.csh S1A_IW_SLC__1SDV_20190704T135158_20190704T135225_027968_032877_1C4D.SAFE S1A_IW_SLC__1SDV_20190716T135159_20190716T135226_028143_032DC3_512B.SAFE config.tops.txt >& log.txt &

If you want to change the default processing parameters use :doc:`pop_config.csh` to create a 
default configuration file, and edit as necessary.

    




