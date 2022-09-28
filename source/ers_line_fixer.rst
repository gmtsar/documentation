.. index:: ! ers_line_fixer       

**************      
ers_line_fixer    
**************      

Synopsis
--------
**ers_line_fixer**  *[ -a near_range] [ -h header ] [ -l line ] [ -s station ] <raw file> <fixed file>*


Description
-----------
**ers_line_fixer**                       

Required Arguments
------------------

*raw file*          

	Input filename

*fixed file*       

	Output filename 

Optional Arguments
------------------
   
**-a**  *near_range*      

	Align near_range 

**-h**  *header*         

	Set the header length (bytes)

**-l**  *line*           

	Set the line length (bytes)

**-s**  *station*        

	Set processing station. Station options: DPAF/ESRIN, CO, EIC, UK, CCRS, ASF, Unknown

Example
-------
 ::

    ers_line_fixer 



