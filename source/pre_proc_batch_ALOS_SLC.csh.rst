.. index:: ! pre_proc_batch_ALOS_SLC.csh

**************
pre_proc_batch_ALOS_SLC.csh
**************

Synopsis
--------
**pre_proc_batch_ALOS_SLC.csh** *data.in batch.config* 

Description
-----------
**pre_proc_batch_ALOS_SLC.csh** Preprocess a set of ALOS images using a common rear_range and radius 


       format of data.in is:
 
         line 1: master_name 
 
         line 2 and below: aligned_name


       example of data.in for ALOS is:
 
         IMG-HH-ALPSRP096010650-H1.0__A
 
         IMG-HH-ALPSRP089300650-H1.0__A
 
         IMG-HH-ALPSRP236920650-H1.0__A


Note: If you need to create a default config file, use :doc:`pop_config.csh`

Example
-------
  **pre_proc_batch_ALOS_SLC.csh** data.in batch.config 
