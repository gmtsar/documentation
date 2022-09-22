.. index:: ! phasefilt            

************      
phasefilt         
************      

Synopsis
--------
**phasefilt** *-imag imag.grd -real real.grd [-alpha alpha][-psize size][-amp1 amp1.grd -amp2 amp2.grd][-diff][-v]*


Description
-----------
**phasefilt** Applies Goldstein adaptive filter to phase [output: filtphase.grd] or applies modified Goldstein adaptive filter to phase [output: filtphase.grd, corrfilt.grd]

  imag        -  [required] GMT format file of imaginary component

  real        - [required] GMT format file of real component

  alpha       -	exponent for filter - usually between 0.0 and 1.5 (0.0 should not filter).
		default: 0.5	[Goldstein filter] (anything above 1.0 may be excessive)
		alpha < 0 will set alpha = (1 - coherence) [modified Goldstein]

  psize       -	patch size for filtering. Must be power of two.
		default: 32

  amp1 	      -	GMT format file of amplitude image of image 1. Needed (and applies) modified filter.

  amp2 	      -	GMT format file of amplitude image of image 2. Needed (and applies) modified filter.

  diff        - Calculate difference between input phase and output phase.

  complex_out -	Write out filtered real and imaginary (filtphase_real.grd and filtphase_imag.grd)

  v           - Verbose.

  debug       -	Debug.
             



Example
-------
    **phasefilt** -imag imag.grd -real real.grd -alpha 0.5



