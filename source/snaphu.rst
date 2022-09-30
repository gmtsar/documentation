.. index:: ! snaphu               

******      
snaphu            
******      

Synopsis
--------
**snaphu** *[options] infile linelength [options]*


Description
-----------
**snaphu** Unwrapping phase                       
   
Required Arguments
------------------

*infile*

	Input file

*linelength*

	

Optional Arguments
------------------
 
Most common options:

**-t**              use topography mode costs (default)

**-d**              use deformation mode costs

**-s**              use smooth-solution mode costs

**-C** *<confstr>*    parse argument string as config line as from conf file

**-f** *<filename>*   read configuration parameters from file

**-o** *<filename>*   write output to file

**-a** *<filename>*   read amplitude data from file

**-c** *<filename>*   read correlation data from file

**-M** *<filename>*   read byte mask data from file

**-b** *<decimal>*    perpendicular baseline (meters)

**-i**              do initialization and exit

**-S**              single-tile reoptimization after multi-tile init

**-l** *<filename>*   log runtime parameters to file

**-u**              infile is already unwrapped; initialization not needed

**-v**              give verbose output

**--mst**           use MST algorithm for initialization (default)

**--mcf**           use MCF algorithm for initialization

**--tile** <nrow> <ncol> <rowovrlp> <colovrlp>  unwrap as nrow x ncol tiles

**--nproc** *<integer>*               number of processors used in tile mode


Note: type snaphu -h for a complete list of options


Example
-------
 ::

    snaphu



