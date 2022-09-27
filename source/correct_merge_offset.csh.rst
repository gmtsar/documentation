.. index:: ! correct_merge_offset.csh

************************
correct_merge_offset.csh
************************

Synopsis
--------
**correct_merge_offset.csh** *merge_list merge_log input.grd output.grd*

Description
-----------
**correct_merge_offset.csh** used to correct offset between subswaths after merging (e.g. caused by range time diff)   

Required Arguments
------------------

*merge_list*

	List of input files for merge

*merge_log*

	Log output from the merging process

*input.grd*

	Grid file to be corrected

*output.grd*

	Name of corrected output grid

Example
-------
 ::

    correct_merge_offset.csh merge.list merge_log phasefilt.grd phasefilt_mcor.grd 
