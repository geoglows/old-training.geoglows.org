.. _Met Data Explorer:

.. |info_metadata_var| image:: /_static/imgs/met-data-explorer/info_metadata_var.png

.. |disp_settings| image:: /_static/imgs/met-data-explorer/disp_settings.png

.. |left| image:: /_static/imgs/met-data-explorer/left.png

.. |filter| image:: /_static/imgs/met-data-explorer/filter.png



The Met Data Explorer
=====================

In recent years, there has been a growing recognition of the need for standardized ways of sharing meteorological gridded data on the web.
In response to this need, Unidata, a division of the University Corporation for Atmospheric Research (UCAR) developed the `THREDDS Data Server <https://github.com/Unidata/thredds>`_ (TDS).
TDS is a web server that provides metadata and data access for scientific datasets, using OPeNDAP, OGC WMS and WCS, HTTP, and other remote data
access protocols.

In order to extract data from the TDS, many tools were developed such as the `grids <https://tsgrids.readthedocs.io/en/stable/>`_ python package.
The grids package allows for extracting time series subsets from n-dimensional arrays in NetCDF, GRIB, HDF, and GeoTIFF formats.
Met Data Explorer (MDE) is a newly developed web-based tool allowing a broad range of users to discover, access, visualize, and
download data from any TDS that stores available meteorological data using the grids package. MDE was also designed in a way that
allows users to customize it for local or regional web portals.

MDE is an open-source web application providing users with the functionalities of data discovery, data access, data visualization,
and data downloading from any TDS. MDE  can be installed by any organization and requires minimal server space.

The MDE is an open-source web application for visualizing meteorological gridded data. Utilizing TDS to serve the data, the application
allows you to organize and save data files with the specific variables and dimensions that you need, visualize the data in a
Leaflet based map viewer, animate the data across a time series, and extract a time series over a specified area.
The area for extraction can be specified as a marker, bounding box, or polygons. To extract a time series, the application utilizes
the grids python to remotely access and extract the data over the given area. The time series extraction
feature in the MDE will work on most data, provided that the data conforms to OGC3 standards and the TDS is properly configured.

Functionalities Demonstration
*****************************

This demo will explain how to use the WDE functionalities as a regular user, without admin permissions. We will be using
the “G1” Catalog, with the following TDS “Mekong”, “AROME”, and "GFS" These TDS should be preloaded in the `tethys staging portal <https://tethys-staging.byu.edu/apps/>`_ by
a aministrator user before using them. The Demonstration will wlak the user through the discovery, visualization, and downloading of the data.

Data Discovery
--------------

The first step is to select a TDS file title and click on it. This will cause the graphs panel to open,
and the first variable of the TDS file will be displayed on the map using Web Mapping Services(WMS).
The appearance of the TDS file variable can be change by pressing on the |disp_settings| icon as shown in the image below.

.. image:: /_static/imgs/met-data-explorer/1.7.png
   :width: 1000
   :align: center

.. note::
   The display settings allows to change the opacity and color style of the WMS layer beloging to the TDS file variable.
   It also allows the user to find or enter manually the data bounds of the TDS file variable.

You can use the |left| icon to see the available variables of the selected TDS file. A table displaying all the variables found in the TDS file is generated.
The table will also show you the dimensions and metadata of each variable.

.. image:: /_static/imgs/met-data-explorer/1.8.png
   :width: 1000
   :align: center

.. note::
   In order to see the metadata of a variable press in the button with the |info_metadata_var| icon.

.. image::/_static/imgs/met-data-explorer/1.9.png
   :width: 1000
   :align: center

You can see the metadata of the selected TDS file from the TDS file variable list with the
|left| icon. A table displaying the metadata properties of the selected TDS file will appear.


.. image:: /_static/imgs/met-data-explorer/1.2.png
   :width: 1000
   :align: center

.. note::
   The metadata properties for each TDS file are different and depends on the data source provider.



Finally, you can filter the available TDS files by variable of interest by using the |filter| icon.

.. image:: /_static/imgs/met-data-explorer/1.6.png
   :width: 1000
   :align: center

Time Series Visualization and Downloading
-----------------------------------------

You can visualize and download available time series for a specific TDS variable. First, select the
variable of interest on the WDE map interface. There will be three different methods to retrieve timeseries from a
selected variable: "Drawing on map" and "adding a shape feature" such as a shapefile or WMF GeoServer link.

.. note::
   Only time series from variables with 3 dimensions can be plotted using a shapefile and WMF GeoServer link. If a variable
   contains more than 3 dimensions the "Drawing on a map" method should be selected. Timeseries using a marker or bounding box
   are supported for variables with more than 3 dimensions.

Draw on the Map
---------------

The "Draw on map" options allows you to draw a marker, bounding box or polygon in the map using the drawing palette in
the map.

The steps to retrieve Time series using the "Draw on Map" method are the following:

1. Select the variable of interest.
2. Select the option "Draw on Map".
3. If the variable has more than 3 dimensions, then provide a value for the 4th dimension.
4. Select the type of plots.
5. Plot the time series.
6. Download in the desired format.

.. image:: /_static/imgs/met-data-explorer/1.10.png
   :width: 1000
   :align: center

.. note::
   The 4th dimension is other than time, latitude or longitude. The different values r value for the 4th dimension are found by the MDE automatically.
   The value for the 4th dimension can be found manually by opening the OPeNDAP service in your browser and looking for the name of the variable.
   For example, a dimension called isobaric will be listed in the OPeNDAP service in the following way: isobaric1: Array of 32 bit Reals [isobaric1 = 0..40]. This means that the value of the
   4th dimension can be any between 0 to 40.


Adding a Shape Feature
----------------------

The "Adding a Shape Feature" option allows you to upload a shape feature from a shapefile or WMF GeoServer link in the map and extract time series
from a property that is in all the features of the shapefile. For example, if every feature of a shapefile contains a property called "id", then a time serie for each feature will be
retrieved.

.. note::
   Before adding a shape feature, the shapefile or WMF GeoServer service used must have an attribute shared by each feature with unique values.
   The app will use this attribute to label the features when a time series is extracted.

The first option is to upload a shapefile which will be converted and stored as a geojson in the app. In order to see the dialogue box to upload a shapefile,
select this option from the dropdown menu as shown in the figure below.

.. image:: /_static/imgs/met-data-explorer/1.12.png
   :width: 1000
   :align: center

The second option is to access a geojson feature through a Geoserver or other application that provides WFS (Web Feature Service) access.
In order to see the dialogue box to submit the WFS service URL, select this option from the dropdown menu as shown in the figure below.

.. image:: /_static/imgs/met-data-explorer/1.13.png
   :width: 1000
   :align: center

The steps to retrieve Time series using the "Adding a Shape Feature" method are the following:

1. Select the variable of interest.
2. Select between the options: "Use a Shapefile" or "WMF GeoServer Link".
3. Upload the shapefile or provide the WMF service URL.
4. Provide the behavior type: dissolve or features.
5. If you select the "features" type for the behavior type, then select an attribute shared by each feature in the shapefile or WMF service URL that contains unique values.
6. Select the type of plots.
7. Plot the time series.

.. image:: /_static/imgs/met-data-explorer/1.11.png
   :width: 1000
   :align: center

.. note::
   The behavior type determines how the vector data is used to mask the arrays. Options are: dissolve, features - dissolve:
   treats all features as if they were 1 feature and masks the entire set of polygons in 1 grid - features:
   treats each feature as a separate entity, must specify an attribute shared by each feature with unique values
   for each feature used to label the resulting series

Additional Resources
********************

- MDE source code `<https://github.com/BYU-Hydroinformatics/Met-Data-Explorer>`_

- Grids Documentation <https://tsgrids.readthedocs.io/en/stable/>`_
