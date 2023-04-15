.. index:: ! S1_Batch_Preprocessing

**********************
S1_Batch_Preprocessing  
**********************

This page covers the necessary set up and details for each step of the
batch processing workflow for Sentinel-1 data:

    * Directory Setup  
    * Organizing Data & Region Coverage Clipping and Stitching
    * Linking Data
    * Preprocessing Mode I: Choosing a Reference Image
    * Preprocessing Mode II: Aligning to Reference Image


Directory Setup 
---------------

The first thing to do to prepare for batch processing is to organize your
directory structure into the following path tree, for example, a descending track:

 ::

				[des]
				  |
	  ________________________|________________________________		
          |       |        |        |     |    |    |      |      |
	[data] [orbit] [reframed] [topo] [F1] [F2] [F3] [SBAS] [merge]
					  |    |    |
			          ________|_________________________
				  |     |       |       |          |
				[raw] [SLC] [intf_in] [topo] batch_tops.config	

The directories are:

    * [data] is where you store your .SAFE files downloaded from ASF or Copernicus
    * [orbit] is where you store your orbit (.EOF) files
    * [reframed] is where you store your coverage area pins if you want to clip or stitch frames together
    * [topo] is where you store your downloaded DEM file
    * [F1], [F2], and [F3] are your subswath-specific processing directories (where you will preprocess your data and calculate your interferograms). Each should share the same subdirectory structure.
    * [SBAS] is where you will eventually process your time series (at a later point)
    * [merge] is where you will merge and store you merged interferograms (unless you choose to process only one subswath of Sentinel-1 data over you area)

The structure of the [F1], [F2], and [F3] subdirectories should be the same in each:

    * [raw] is where you store your prepared raw data and orbit files, and where you will process your raw data into coregistered SLC files
    * [SLC] is where you can store final SLC files
    * [intf_in] is where interferograms will be calculated and stored
    * [topo] is another directory where you will store a linked copy of your DEM file
    * batch_tops.config: A copy needs to be stored in each F1/2/3 directory you want to process data for. This will be your main config file for interferogram processing. You can download one from the GMTSAR github if you do not have one already. 

Once your DEM file is stored in des/topo/ (check out :doc:`Generating_DEM` to learn more), you can link it to your F1 directory:

 ::

    cd F1/topo
    ln -s ../../topo/dem.grd .

And do that for each F2 and F3 directory you plan to process. 


Organizing Data & Coverage Clipping & Stitching
-----------------------------------------------

This is an *optional* step for anyone who wants to cover a larger area than one single Sentinel-1
frame. Skip this step if you only want to process one frame.

*Choosing Stitch Points*

You can choose to stitch multiple frames from the same track together to make a larger coverage
area. This only works for frames within the same track (and only the same ascending OR descending track,
they cannot be mixed). 

First you must define your region of interest covered by the frames you want to stitch together.
The most straightforward way to do this is to plot the .SAFE file preview KML files in Google Earth
(Check inside your .SAFE file under preview/map_overlay.kml).

One you have those loaded, pick your stitch point (pin) locations of where you want your coverage to start and stop.

**CRITICAL** When you pick your pin locations, they must be in the order of the satellite data collection. For instance, for a descending track set of frames, the first lon/lat point must be the point that is closest to the north, or top of the image, while the second point must be further south of the first pin point. For ascending data, the first point must be a point closest to the south of the image.

When you pick your points, create a file called "pins.ll" and place your lon/lat locations in the correct
ascending or descending order. Then place this pins.ll file into the reframed/ directory.

   * TIP: If you are trying to cover a large area with many frames, you may need multiple stitch points (a rule of thumb is make sure to have one approximately every ~150 km).

   * TIP: Pay attention to the projected bounds of your coverage. To pick a working pin location, it must be in a position that has data across the latitude along the entire data file (i.e., if you pick a pin location on a corner of the image it may not be successful unless the corner lines up with available data)

*Running organize_files_tops*

The tool that does the actual stitching of frames together is called :doc:`organize_files_tops.csh`.
Note that there is both a unix and a linux version (:doc:`organize_files_tops_linux.csh`)

This script will download the precise orbit files for you if you have not previously downloaded them.

Inside the data/ directory:

 ::

   # make a list of SAFE files with the absolute path
   ls -d $PWD/*.SAFE > SAFE_filelist

   organize_files_tops.csh SAFE_filelist ../reframed/pins.ll 1 >& oft_mode1.log &

   # or, if you are on a linux machine:
   organize_files_tops_linux.csh SAFE_filelist ../reframed/pins.ll 1 >& oft_mode1.log &

   # optional: to watch the screen output, tail the log file
   tail -f oft_mode1.log

   # when finished, check the log file for any errors

Mode 1 of :doc:`organize_files_tops.csh` will go through and make sure you have orbit files and will tell
you which dates of SAFE files it will be able to re-organize and stitch together for you. Mode 2 is the 
part that actually completes the stitching.

To run mode 2:

 ::

   organize_files_tops.csh SAFE_filelist ../reframed/pins.ll 2 >& oft_mode2.log &
   
   # or, if you are on a linux machine:
   organize_files_tops_linux.csh SAFE_filelist ../reframed/pins.ll 2 >& oft_mode2.log &


Once this is done running, there should be a new directory starting with F????_F???? (there may be multiple new directories). Inside these new directories are your stitched .SAFE files. You can move all files to a single 
F????_F???? directory if desired.

Common Errors/Mishaps:
 
   * Not using *absolute* path in the list of SAFE file names -- you need absolute path, not relative path
   * Stitch points/pins are backwards or not placed correctly (this may manifest as the log file telling you it cannot stitch the frames together)
   * Precise orbits may not be available yet. If you want to process with restituted orbits instead, download them manually, place them in the reframed directory and then run this command for each SAFE file you have that requires a restituted orbit:

 ::

   create_frame_tops.csh "SAFE_file_absPath" "matching restituted orbit name"

Then you can move these final files to the same F????_F???? directory as your other .SAFE files.


Linking Data    
------------   

The next step in preprocessing is to link your data to the raw directory for processing.

For those interested in processing all three subswaths (F1,F2,F3), complete this step in each directory.
For those interested in just processing one or two subswaths, just complete this in the desired subswaths directories.

 ::

    # For users who stitched frames together:
    cd F1/raw
    ln -s ../../data/F*/*.SAFE/*/*iw1*vv*xml .
    ln -s ../../data/F*/*.SAFE/*/*iw1*vv*tiff .

    # For user who did not do any stitching, omit the stitched directory like so:
    ln -s ../../data/*.SAFE/*/*iw1*vv*xml .
    ln -s ../../data/*.SAFE/*/*iw1*vv*tiff .

    # For all:
    ln -s ../../data/*.EOF .
    ln -s ../topo/dem.grd .

NOTE: "iw1" files correspond to the F1 subswath. For F2, change the above to "iw2" and for F3, "iw3".


Preprocessing Mode I
--------------------

*Page in progress*

Preprocessing Mode II
---------------------

*Page in progress*
