.. _installation_win64:

*******************************
Installation in Windows 64 bit
*******************************

.. |br| raw:: html

 <br />

.. _QGIS_installation_win64bit:
 
QGIS download and installation
------------------------------------------

* Download the latest QGIS version 64 bit from `here <http://www.qgis.org/en/site/forusers/download.html>`_ (the direct download of QGIS 2.2 from this `link <http://qgis.org/downloads/QGIS-OSGeo4W-2.2.0-1-Setup-x86_64.exe>`_);

* Execute the QGIS installer with administrative rights, accepting the default configuration.

Now, QGIS 2 is installed.

.. image:: _static/QGIS.jpg

.. _scipy_installation_win64bit:
 
SciPy installation
------------------------------------------

The SciPy package is not included in the 64 bit version of QGIS. Therefore:

* Download scipy-0.13.3.win-amd64-py2.7.exe for Windows 64 bit `from here <http://www.lfd.uci.edu/~gohlke/pythonlibs/#scipy>`_ (provided by Christoph Gohlke, Laboratory for Fluorescence Dynamics, University of California, Irvine).

* Extract the file scipy-0.13.3.win-amd64-py2.7.exe with `7-zip <http://www.7-zip.org/>`_ in a temporary directory;

* Copy all the files contained in the PLATLIB directory inside the QGIS directory, which should be::

	C:\Program Files\QGIS Valmiera\apps\Python27\Lib\site-packages

.. _plugin_installation_win64bit:
 
Semi-Automatic Classification Plugin installation
---------------------------------------------------

* Run QGIS 2;

* From the main menu, select Plugins > Manage and Install Plugins;

.. image:: _static/install.jpg

* From the All menu, select the Semi-Automatic Classification Plugin and click the button Install plugin;

.. image:: _static/plugins.jpg

* The plugin should be automatically activated; however, be sure that the Semi-Automatic Classification Plugin and Processing are checked in the Installed menu.

.. image:: _static/plugins_installed.jpg

.. _plugin_configuration_win64bit:

Configuration of the Processing plugin
------------------------------------------

This configuration is required because SAGA GIS needs to be activated in the Processing framework of QGIS 2.

* Select the menu Processing > Options and configuration; 

.. image:: _static/conf.jpg

* Click the + symbol beside Providers, and click the symbol + beside SAGA;

.. image:: _static/processing_SAGA.jpg

* SAGA should be already configured. However, verify the following settings:
	#. The checkbox Activate is checked;
	#. Important! Because SAGA 2.0.8 was installed, the checkbox Enable SAGA 2.0.8 compatibility must be checked; if SAGA 2.1.0 was installed then it must be unchecked;
	#. The path in SAGA folder points to::
		
		C:/PROGRA~1/QGISVA~1/apps\saga

Now, the Semi-Automatic Classification Plugin is installed and configured. The plugin is available under the Raster menu of QGIS, or you can click the icon |logo| in the main interface (if the raster menu is activated).

.. |logo| image:: _static/logo.png
	:width: 32pt
	
.. image:: _static/activated.jpg
