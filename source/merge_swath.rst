.. index:: ! merge_swath          

***********      
merge_swath       
***********      

Synopsis
--------
**merge_swath** *inputlist output [stem] [n1 n2]*


Description
-----------
**merge_swath** Merging subswaths                       

Required Arguments
------------------
   
 
*inputlist*

	List of input files per subswath 

	Format example: 

		F1/intf/2015036_2015060/S1A_20150609.PRM:F1/intf/2015036_2015060/phasefilt.grd

                F2/intf/2015036_2015060/S1A_20150609.PRM:F2/intf/2015036_2015060/phasefilt.grd

                F3/intf/2015036_2015060/S1A_20150609.PRM:F3/intf/2015036_2015060/phasefilt.grd

	Note: use the aligned PRM which contains the shift information

*output*

	output.grd [stem.PRM]

note: please put the files to stem.in in the order of swath numbers.

      make sure all images have same num_rng_bin

      the n1 and n2 will determine where to stitch, they have to be

      pairs when assigned. In case you have only two, use 0 for n2



Example
-------
 ::

    merge_swath  



