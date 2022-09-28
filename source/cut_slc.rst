.. index:: ! cut_slc              

*******      
cut_slc           
*******      

Synopsis
--------
**cut_slc** *stem.PRM new_stem range [prm_only]*


Description
-----------
**cut_slc** program for cutting SLC images                       

Output: new_stem.PRM new_stem.SLC (old .LED file can still be used)

Required Arguments
------------------

*stem.PRM*        

	PRM file for coregistered image to be cut

*new_stem*        

	Name stem for newly generated SLC and PRM file

*range*           

	Range to cut the SLC as min_range/max_range/min_azimuth/max_azimuth (e.g., 500/1500/900/3600)



Example
-------
 ::

    cut_slc S1_20190809_ALL_F1.PRM S1_20190809_F1_cut 500/1500/900/3600 



