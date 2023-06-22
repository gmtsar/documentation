.. index:: ! Batch_Preprocessing

**********************
Batch_Preprocessing  
**********************

This page covers the necessary set up and details for each step of the
batch processing workflow for non-Sentinel-1 data:

    * Directory Setup  
    * Preprocessing: Choosing a Reference Image
    * Alignment: Aligning images to a Reference Image 


Directory Setup 
---------------

The first thing to do to prepare for batch processing is to organize your
directory structure into the following path tree, for example, for a given track:

 ::

                              [track#]
                                  |
                          ________|_______             
                           |      |     |    
                         [raw] [topo] [intf]
                                          

The directories are:

    * [raw] is where you store your SAR data and preprocess your data
    * [topo] is where you store your downloaded DEM file
    * [intf] is where your interferograms will be stored

Preprocessing
-------------

The first step of preprocessing your data is to calculate and plot a baseline diagram
showing the placement of all your chosen input images in your batch. To accomplish this, you first
need to create a data.in file, which is the input file for :doc:`pre_proc_batch.csh` . All preprocessing
occurs in the raw directory.


*Creating data.in*

The data.in file is a list of SAR image namestems — see :doc:`pre_proc_batch.csh` to see how to 
format a data.in file for your given data type. 

*NOTE*: The first line in your data.in file should be your reference image, but you will need to 
run this once to get your baseline_table and your baseline.ps plot to see how your images plot together.

Alignment
---------

The second step of preprocessing your data is to align all your images to your chosen reference
image. See :doc:`align_batch.csh` to see the usage for this tool. You will need to create an align.in
file for this purpose.

Once all your images are aligned to their reference image, you are ready to start processing 
interferograms.

