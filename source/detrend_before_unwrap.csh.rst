.. index:: ! detrend_before_unwrap.csh

************************
detrend_before_unwrap.csh
************************

Synopsis
--------
**detrend_before_unwrap.csh** *master number  bounds*

Description
-----------
**detrend_before_unwrap.csh**

  master  -  is the stem name for the master image, eg. ALOS2040533050-150222-WBDR1.1__D

  number  -  is the frame number (1-5) to use for detrending

  bounds  -  (eg. 0/1000/0/1000) is the GMT bounds in range/az coordinates to use

Example
-------
**detrend_before_unwrap.csh** ALOS2040533050-150222-WBDR1.1__D 3 0/1000/0/1000 
