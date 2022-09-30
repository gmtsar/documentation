.. index:: ! prep_sbas.csh  

*************
prep_sbas.csh 
*************

Synopsis
--------
**prep_sbas.csh** *intf.in baseline_table.dat file_path phase_name corr_name*

Description
-----------
**prep_sbas.csh** will prepare two input files for the :doc:`sbas` program

This program outputs:

**intf.tab**                

	The table of interferogram information used as input to :doc:`sbas`

**scene.tab**               

	The list of scenes included in your time series as input to :doc:`sbas`

**sample_sbas_command**     

	A command is echoed showing the required parameters to create a time series from your chosen interferograms.

Required Arguments
------------------
  
*intf.in*                 

	The input file for :doc:`intf_tops.csh`

*baseline_table.dat*      

	The full baseline_table.dat file (use :doc:`get_baseline_table.csh` if missing)

*file_path*               

	The location of your merged interferogram directories you want to include in your SBAS process

*phase_name*              

	The filename and/or location and name of your unwrapped interferograms. This program will assume the named file is inside the specific date1_date2 directory of the interferogram, unless you specify a next level directory inside the date1_date2 directory inside which your interferogram is stored (e.g. in the example below, inside the date1_date2 directories is another directory called "corrected" inside which is the unwrap.grd we want to use, or in path form: ../merge/date1_date2/corrected/unwrap.grd ).

*corr_name*               

	The filename and/or location and name of your correlation grids (see above note for *phase_name* about specifying the location of your grid files) 



Example
-------
 ::

    prep_sbas.csh intf.in baseline_table.dat ../merge corrected/unwrap.grd corr.grd
