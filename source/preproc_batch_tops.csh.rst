.. index:: ! preproc_batch_tops.csh

**************
preproc_batch_tops.csh
**************

Synopsis
--------
**preproc_batch_tops.csh** *data.in dem.grd mode* 

Description
-----------
**preproc_batch_tops.csh** preprocess and align a set of tops images in data.in, precise orbits required 


Input:

  data.in  -   input file list of specific SAFE measurement file root names and their respective orbit files, formatted as below. To automatically create `data.in` use :doc:`prep_data.csh` or :doc:`prep_data_linux.csh`.
             
               format of data.in:

                    image_name:orbit_name

               example of data.in

                    s1a-iw1-slc-vv-20150626...001:s1a-iw1-slc-vv-20150626...001:s1a-iw1-slc-vv-20150626...001:S1A_OPER_AUX_POEORB_V20150601_20150603.EOF

                    s1a-iw1-slc-vv-20150715...001:s1a-iw1-slc-vv-20150715...001:s1a-iw1-slc-vv-20150715...001:S1A_OPER_AUX_POEORB_V20150625_20150627.EOF

   dem.grd -   DEM file located in the `topo` folder must be linked here

   mode    -   mode = 1 prepares for alignment and creates a baseline-time.ps plot to choose a master image, while mode=2 does the actual alignment (user-chosen master image must be promoted to the first line in data.in before mode 2 is run).


Output:

    baseline.ps align_table.ra (contains info for precise geomatric alignment)
    
    Mode 2 produces the final *.PRM *.LED and aligned *.SLC files

  Note:
    The names must be in time order in each line to be stitched together

Reference: Xu, X., Sandwell, D.T., Tymofyeyeva, E., González-Ortega, A. and Tong, X., 
    2017. Tectonic and Anthropogenic Deformation at the Cerro Prieto Geothermal 
    Step-Over Revealed by Sentinel-1A InSAR. IEEE Transactions on Geoscience and 
    Remote Sensing. https://doi.org/10.1109/TGRS.2017.2704593 


Example
-------
  **preproc_batch_tops.csh** data.in dem.grd 1 
