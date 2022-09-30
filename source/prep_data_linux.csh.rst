.. index:: ! prep_data_linux.csh  

*******************
prep_data_linux.csh 
*******************

Synopsis
--------
**prep_data_linux.csh** 

Description
-----------
**prep_data_linux.csh** will create a data.in file that is a primary input for :doc:`preproc_batch_tops.csh` on a linux system. 

To run, all data files (.xml and .tiff) and orbit files (.EOF) must be located in the run directory (usually **raw**). If a "data.in" file exists it will be removed. 

*WARNING: This currently depends on a connection to an ASF orbit file index*

Example
-------
 ::

    prep_data_linux.csh 
