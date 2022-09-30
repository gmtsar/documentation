.. index:: ! unwrap_parallel.csh

*******************
unwrap_parallel.csh
*******************

Synopsis
--------
**unwrap_parallel.csh** *intflist Ncores* 

Description
-----------
**unwrap_parallel.csh** Unwraps interferograms in parallel

    Run unwrapping jobs parallelly. Need to install GNU parallel first.

    Also required is a script called unwrap_intf.csh, which must be manually created

    Note, run this in the directory where all the interferograms are stored as date1_date2 directories (this can be **intf_all/** if just unwrapping one subswath, or can be in **merge/** if unwrapping merged data).  

Required Arguments
------------------

*intflist*

	List of interferograms to be unwrapped (listed as date1_date2, in YYYYDDD_YYYYDDD format)

*Ncores*

	Specify how many cores you wish to use for parallel processing. 

	*WARNING*: Be aware how many cores your machine has before choosing a Ncores value.


Example
-------
 ::

    unwrap_parallel.csh 
