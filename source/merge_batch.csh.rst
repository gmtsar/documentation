.. index:: ! merge_batch.csh

**************
merge_batch.csh
**************

Synopsis
--------
**merge_batch.csh** *inputfile config_file [det_stitch]*

Description
-----------
**merge_batch.csh** will apply :doc:`merge_unwrap_geocode_tops.csh` to the given list of interferogram pairs. The list must be formatted as the example below. Additionally, `merge_batch.csh` allows the option of calculating a det_stitch parameter which will calculate the stitching position based on existing NaN areas in the given grid file. 


Input: 
   
   inputfile    -   list of input interferogram pair parameter files, formatted as:

      IF1_Swath1_Path:master.PRM:repeat.PRM,IF1_Swath2_Path:master.PRM:repeat.PRM,IF1_Swath3_Path:master.PRM:repeat.PRM

      IF2_Swath1_Path:master.PRM:repeat.PRM,IF2_Swath2_Path:master.PRM:repeat.PRM,IF1_Swath3_Path:master.PRM:repeat.PRM

      (Use the repeat PRM which contains the shift information.)

      e.g. ../F1/intf_all/2015092_2015128/:S1A20150403_ALL_F1.PRM:S1A20150509_ALL_F1.PRM,../F2/intf_all/2015092_2015128/:S1A20150403_ALL_F2.PRM:S1A20150509_ALL_F2.PRM,../F3/intf_all/2015092_2015128/:S1A20150403_ALL_F3.PRM:S1A20150509_ALL_F3.PRM

      Input file notes: 

      + Make sure that under each path, the processed phasefilt.grd, corr.grd and mask.grd exist. Also make sure the dem.grd file is linked in your working merge/ directory

      + The master image of the batch must be listed in a pair in the first line of your input list (e.g. a masterdate_secondarydate pair)


   config_file  -    the same config file used for interferogram processing (e.g., batch.config or batch_tops.config)   

   det_stitch   -   set det_stitch to 1 if you want to calculate the stitching position based on the NaN area in the grids


Output: 

   One directory for each pair, inside which will be the merged corr.grd, phasefilt.grd and mask.grd prodcts.

  Note: If the trans.dat file already exists, this command will not recompute the projection matrix (and will not overwrite the existing trans.dat file).

Example
-------
**merge_batch.csh** filelist batch.config 
