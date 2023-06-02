.. gmtsar documentation master file, created by
   sphinx-quickstart on Tue Jan 19 14:02:36 2021.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

GMTSAR Documentation
====================

Welcome to the documentation page for GMTSAR software!

GMTSAR is an open-source SAR processing system that enables users
to complete data preparation, processing, and post-processing presentation
all within one workflow system. This website contains searchable documentation
for all active GMTSAR scripts and modules, as well as examples and 
recommended workflows for processing interferograms from multiple
satellite sources, as well as processing InSAR time series. 

Explore the tools, workflows and resources below!

.. toctree::
   :hidden:

.. panels::
    :container: container-lg pb-3
    :column: col-lg-12 p-2
    
    :img-top: _static/01_rc_intf_header.png
    .. toctree::
        :maxdepth: 1
        :caption: Processing An Interferogram

        Installation
        Quick_Start_Guide  
        Core_Processing_Scripts 
        Interferogram_Examples 
 
    ---
    :img-top: _static/02_batch_proc_header.png
    .. toctree::
        :maxdepth: 1
        :caption: Batch Processing and Time Series

        Batch_Processing_Guide  
        Core_Batch_Processing_Scripts 
        Time_Series_Examples  
        
    ---
    :img-top: _static/03_presentation_header.png
    .. toctree::
        :maxdepth: 1
        :caption: Getting the Most Out of Your Data

        Guide_To_Interferogram_Corrections 
        Projecting_To_LatLon

    ---
    .. toctree::
        :maxdepth: 1
        :caption: Additional Resources      

        Installation
        Learning_More_About_InSAR
        Frequently_Asked_Questions 
        Citation_and_Funding_Information
        License <https://github.com/gmtsar/gmtsar/blob/master/LICENSE.TXT>

    ---

    .. toctree::
        :maxdepth: 1
        :caption: Contents

        modules


Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
