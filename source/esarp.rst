.. index:: ! esarp

*****
esarp
*****

Synopsis
--------
**esarp** *input.PRM* *output.SLC* [R4]

Description
-----------
**esarp** reads in parameters specified in *input.PRM*, with the orbit file specified as **led_file** and 
raw data specified as **input_file**, and produce focused Single Look Complex **(SLC)** file. 

Required Arguments
------------------

*input.PRM*

	Input parameter file

*output.SLC*

	output SLC file

Optional Argument
-----------------

*R4*

	

Example
-------
 ::

    esarp IMG-HH-ALPSRP049040660-H1.0__A.PRM IMG-HH-ALPSRP049040660-H1.0__A.SLC 
