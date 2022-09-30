.. index:: ! phasediff_get_topo_phase

************************      
phasediff_get_topo_phase
************************      

Synopsis
--------
**phasediff_get_topo_phase** *ref.PRM rep.PRM [-topo topo_ra.grd] [-model modelphase.grd]*


Description
-----------
**phasediff_get_topo_phase** Compute phase difference of two images and get topo phase

Note: topo_ra and model in GMT grd format    


Required Arguments
------------------

*ref.PRM*

	Parameter (PRM) file for the reference or master image

*rep.PRM*

	Parameter (PRM) file for the repeat or secondary image

Optional Arguments
------------------

**-topo** *topo_ra.grd*

	Topography	

**-model** *modelphase.grd*

	Modeled phase


Example
-------
 ::

    phasediff_get_topo_phase



