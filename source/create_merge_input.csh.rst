.. index:: ! create_merge_input.csh

**********************
create_merge_input.csh
**********************

Synopsis
--------
**create_merge_input.csh** *intf_list path mode*

Description
-----------
**create_merge_input.csh** Used to create inputlist for merge_batch.csh 

Required Arguments
------------------

*intf_list*   

	Is the folder names in F?/intf_all

*path*       

	The path to your F* directories (usually "..")

*mode*     

	Delineates which subswaths you want to merge

                  mode = 0 is merging all 3 subswaths

                  mode = 1 is for F1/F2

                  mode = 2 is for F2/F3

Example
-------
 ::

    create_merge_input.csh intflist .. 0 
