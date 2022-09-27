# Documentation
GMTSAR documentation

First install sphinx and rtd theme through pip.

How to add a module:
1) go to source, copy a module to a new_module_name.rst
2) edit the file, change names, add description, usage, examples
3) add this new_module_name to module.rst
4) go to documentation and run `make html`, then check build/html/index.html

## Formatting Structure

Check out source/ALOS_merge.rst as an example of formatting for each documentation page (.rst file).

Three main structure rules are suggested to maintain consistency:
1) Subheadings are delineated by "underlining" your subheader text with "----" characters. The main subheadings are **Synopsis**, **Description**, **Required Arguments**, [ **Optional Arguments** , if necessary], and **Example**. In addition, if specific tools have Citations/References, they are listed in a **References** subheading at the bottom.

2) Underneath **Synopsis**, the name of the tool is bolded with two asterisks characters on either side of the word, and all generic argument names are italicized with single asterisks on each side of the argument name (e.g., `*inputfile*`)

3) Underneath **Required Arguments** input file names are listed with their names starting in the first character column, in italics. The description of the input argument is placed two carriage returns and a tab over beneath the name. 

4) To link another documentation page to the page you are working on, you must reference the exact name of the other tool page. To build the link, type `:doc: ``` `name` ``` ` (e.g., if I wanted to link to preproc_batch_tops.csh, I'd make a link like ` :doc: ``` `preproc_batch_tops.csh` ``` ` ). When the html pages are built, the links will be visible and usable. 
