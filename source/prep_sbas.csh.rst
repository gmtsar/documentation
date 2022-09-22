.. index:: ! prep_sbas.csh  

**************
prep_sbas.csh 
**************

Synopsis
--------
**prep_sbas.csh** *intf.in baseline_table.dat file_path phase_name corr_name*

Description
-----------
**prep_sbas.csh** will prepare two input files for the :doc:`sbas` program

Input:
  
  intf.in             -    the input file for :doc:`intf_tops.csh`

  baseline_table.dat  -    the full baseline_table.dat file (use :doc:`get_baseline_table.csh` if missing)

  file_path           -    the location of your merged interferograms you want to include in your SBAS process

  phase_name          -    the filename and/or location and name of your unwrapped interferograms. This program will assume the named file is inside the specific date1_date2 directory of the interferogram, unless you specify a next level directory inside the date1_date2 directory inside which your interferogram is stored (e.g. in the example below, inside the date1_date2 directories is another directory called "corrected" inside which is the unwrap.grd we want to use).

  corr_name           -    the filename and/or location and name of your correlation grids (see above note) 


Output:

  intf.tab            -    The table of interferogram information used as input to :doc:`sbas`

  scene.tab           -    The list of scenes included in your time series as input to :doc:`sbas`

  sample_sbas_command -    A command is echoed showing the required parameters to create a time series from your chosen interferograms.

Example
-------
  **prep_sbas.csh** intf.in baseline_table.dat ../merge corrected/unwrap.grd corr.grd
