.. _classification_dock:

*******************
Classification dock
*******************

.. |br| raw:: html

 <br />

.. image:: _static/Semi-Automatic_Classification.jpg
	:align: right
	:width: 250pt
	
The Classification dock implements the process of **classification** of the image (or only a preview), with several functions for **vector output**, **accuracy assessment** and **classification reports**.

The Classification dock allows for the semi-automatic classification of a remote sensing image (or a band set), using the supervised classification algorithms provided by the SAGA GIS (through the Processing plugin).

The classification process requires a training shapefile containing the ROIs used for the definition of land cover classes (see the :ref:`roi_dock`). It is possible to use the Macroclass ID or Class ID for classifications.

The classification can be performed for the entire image, or for a portion of it, creating a classification preview. Similarly to ROI creation, classification previews are created using the preview pointer, and a click on an image pixel; preview classifications are temporarily placed inside a layer group named ``Class_temp_group``, and they are deleted after that the QGIS session is stopped.

A classification style (i.e. a .qml file) can be used for classifications and previews, allowing for the selection of custom colors for classes.

For each classification, a .tif file is created, with a .csv file which contains the spectral statistics of land cover classes.

Also, it is possible to create automatically the vector output of the classification (a shapefile), calculate the classification accuracy, and apply a mask to the land cover classification (using a polygon shapefile).
	
.. _roi_list:
 
ROI list (Macroclass ID - Class ID - Info)
------------------------------------------

Double click on a ROI item in order to zoom to that ROI in  the map.

* [ ``Select All`` ]: select/unselect all the ROIs;
* [ ``Delete selected ROIs`` ]: delete selected ROIs;
* ``Use Macroclass ID`` : if checked the classification is performed using the Macroclass ID; if unchecked, then the classification is performed using the ID class only.

.. _classification_alg:

Classification algorithm
------------------------


*  ``Select a classification algorithm`` : available classification algorithms are: Maximum Likelihood; Minimum Distance; Spectral Angle Mapping;
* ``Threshold`` : if threshold is equal to 0, then all image pixels are classified; otherwise: 
	* for Maximum Likelihood, pixels are unclassified if probability is less than threshold  value (max 100);
	* for Minimum Distance, pixels are unclassified if distance is greater than threshold value;
	* for Spectral Angle Mapping, pixels are unclassified if spectral angle distance is greater than threshold value (max 90).

.. _classification_preview:

Classification preview
----------------------

* [+]: recall the pointer for the creation of a classification preview ;
* ``Size`` : size in pixel unit of a classification preview (i.e. the side lenght of a square, centered at the clicked pixel);
* [ ``Redo`` ]: create a new classification preview centered at the same pixel of the previous one.

.. _classification_style:

Classification style
--------------------

* [ ``Select qml`` ]: select a previously saved .qml file; this configuration is stored in the QGIS project;
* [ ``Reset`` ]: reset classification and preview styles to default (i.e. colors are automatically assigned to classes).

.. _classification_output:

Classification output
---------------------

* ``Create vector`` : if checked, a shapefile classification is saved into the same folder and with the same name defined for the classification output;
* ``Apply mask`` : if checked, it allows the users to select a shapefile for the purpose of masking the classification;
* ``Classification report`` : if checked, a report about the land cover classification is calculated,  providing the pixel count, the percentage and area for each class; the report is saved as a .csv file in the same folder and with the same name defined for the classification output and the suffix ``_report`` ;
* ``Calculate accuracy`` : if checked, an error matrix of the classification (using ROIs as ground truth) is saved as a .txt file in the same folder and with the same name defined for the classification output;
* [ ``Perform classification`` ]: open a window for the selection of output destination, and perform the image classification that is saved as a .tif file, along with the optional outputs.

|br|

The following is a brief video about the the Classification dock:

http://www.youtube.com/embed/B6zElHi2Pnk?rel=0&amp;start=376&amp;end=763