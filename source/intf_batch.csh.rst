.. index:: ! intf_batch.csh       

**************    
intf_batch.csh    
**************    

Synopsis
--------
**intf_batch.csh** *SAT intf.in batch.config* 


Description
-----------
**intf_batch.csh** make a stack of interferograms listed in intf.in


Required Arguments
------------------

*SAT*

	SAT can be ALOS ENVI(ENVISAT) ENVI_SLC and  ERS

*intf.in*

	Image pairs to calculate interferograms for

	format for intf.in:

		reference1_name:repeat1_name

		reference2_name:repeat2_name

		reference3_name:repeat3_name

		etc.

	*Example of intf.in for ALOS:*

		IMG-HH-ALPSRP096010650-H1.0__A:IMG-HH-ALPSRP236920650-H1.0__A

		IMG-HH-ALPSRP089300650-H1.0__A:IMG-HH-ALPSRP096010650-H1.0__A

		IMG-HH-ALPSRP089300650-H1.0__A:IMG-HH-ALPSRP236920650-H1.0__A


	*Example of intf.in for ERS is:*

		e1_05783:e1_07787

		e1_05783:e1_10292



	*Example of intf.in for ENVISAT is:*

		ENV1_2_127_2925_07195:ENV1_2_127_2925_12706

		ENV1_2_127_2925_07195:ENV1_2_127_2925_13207



	*Example of intf.in for ENVI_SLC is:*

		ASA_IMS_1PNESA20030908_175832_000000182019_00399_07968_0000:ASA_IMS_1PNESA20051121_175837_000000172042_00399_19491_0000

		ASA_IMS_1PNESA20040719_175832_000000182028_00399_12477_0000:ASA_IMS_1PNESA20051121_175837_000000172042_00399_19491_0000

		ASA_IMS_1PNESA20040719_175832_000000182028_00399_12477_0000:ASA_IMS_1PNESA20030908_175832_000000182019_00399_07968_0000

		ASA_IMS_1PNESA20051121_175837_000000172042_00399_19491_0000:ASA_IMS_1PNESA20040719_175832_000000182028_00399_12477_0000

*batch.config*

	Configuration file for making interferogram. It can be created using :doc:`pop_config.csh`

Example
-------
 ::

    intf_batch.csh ALOS intf.in batch.config


