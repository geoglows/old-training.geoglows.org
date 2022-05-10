.. _Met Data Explorer:

.. |add| image:: /_static/imgs/t01.png
    :width: 20

.. |create_group| image:: /_static/imgs/t02.png
    :width: 20

.. |url_go| image:: /_static/imgs/t03.png
    :width: 20

.. |auth_btn| image:: /_static/imgs/t04.png
    :width: 100

.. |auth_add| image:: /_static/imgs/t05.png
    :width: 20

.. |save| image:: /_static/imgs/t06.png
    :width: 40

.. |display| image:: /_static/imgs/t07.png
    :width: 100

.. |marker| image:: /_static/imgs/t08.png
    :width: 20

.. |rectangle| image:: /_static/imgs/t09.png
    :width: 20

.. |polygon| image:: /_static/imgs/t10.png
    :width: 20

.. |shp_dropdown| image:: /_static/imgs/t11.png
    :width: 80

.. |use_shp| image:: /_static/imgs/t12.png
    :width: 80

.. |upload_shp| image:: /_static/imgs/t13.png
    :width: 80

.. |plot| image:: /_static/imgs/t14.png
    :width: 100

.. |download| image:: /_static/imgs/t15.png
    :width: 80

.. |right_arrow| image:: /_static/imgs/t16.png
    :width: 20

.. |info| image:: /_static/imgs/t17.png
    :width: 20

=========================
Met Data Explorer (MDE)
=========================

Introduction
************

In recent years, there has been a growing recognition of the need for standardized ways of sharing meteorological
gridded data on the web. In response to this need, Unidata, a division of the University Corporation for Atmospheric
Research (UCAR) developed the `THREDDS Data Server <https://github.com/Unidata/thredds>`_ (TDS).
TDS is a web server that provides metadata and data access for scientific datasets, using OPeNDAP, OGC WMS and WCS,
HTTP, and other remote data access protocols.

In order to extract data from the TDS, many tools were developed such as the `grids <https://tsgrids.readthedocs.io/en/stable/>`_
python package. The grids package allows for extracting time series subsets from n-dimensional arrays in NetCDF, GRIB,
HDF, and GeoTIFF formats. Met Data Explorer (MDE) is a newly developed, web-based tool allowing a broad range of users
to discover, access, visualize, and download (using the grids package) data from any TDS that stores meteorological data.
MDE was also designed in a way that allows users to customize it for local or regional web portals.

|

.. image:: /_static/imgs/FA.png
   :width: 300
   :align: center

|

MDE is an open-source web application providing users with the functionalities of data discovery, data access,
and data visualization. MDE can be installed by any organization and requires minimal server space.
The MDE is an open-source web application for visualizing meteorological gridded data. Utilizing TDS to serve
the data, the application allows you to organize and save data files with the specific variables and dimensions that
you need, visualize the data in a Leaflet based map viewer, animate the data across a time series, and extract a time
series over a specified area. The area for extraction can be specified as a marker, bounding box, or polygon.
To extract a time series, the application utilizes the grids python to remotely access and extract the data over
the given area. The time series extraction feature in the MDE will work on most data, provided that the data
conforms to OGC3 standards and the TDS is properly configured.

Functionalities Demonstration
*****************************
This tutorial is divided into three parts. The first part of this tutorial introduces the user interface.
The second part explains how to add and organize data in the MDE. Adding data to the MDE requires admin permissions.
The third part of this tutorial explains how to visualize the data in the map interface, define an area over which to
extract the data, plot the extracted time-series, and download the data in a variety of formats. All the steps
explained in the final part of this tutorial can be completed as a regular user, without admin permissions.
If you do not have admin permissions to complete the second part, the preloaded data on the `tethys staging portal <https://tethys-staging.byu.edu/apps/>`_
can be used to complete the final part of this tutorial.

The Interface
-------------
The interface for the MDE is divided into three main sections: the Map Window, the side Navigation Panel, and the
Graph Window (see Figure 1). The Map Window is used for visualizing and animating the data and for defining the
area over which to extract the data. The side navigation panel lists the files that have been loaded into the MDE.
The Graph Window contains all other data-user interactions — including plotting the data, specifying a variable,
and viewing file and variable metadata. The Graph/Map Slider can be used to show or hide the map and graph windows.
The Navigation Panel Toggle can be used to show or hide the navigation panel.

|

.. image:: /_static/imgs/F1.png
   :width: 800
   :align: center

|

Adding Data to the Met Data Explorer
------------------------------------
To add data to the MDE, make sure you are logged in and that your account has the necessary permissions.
Groups, or catalogs, are created to organize the files. Select the Add Group Button |add| (see Figure 2).
The Add Catalog of Thredds Servers dialog will appear (shown in Figure 3).

|

.. image:: /_static/imgs/F2.png
   :width: 800
   :align: center

|

.. image:: /_static/imgs/F3.png
   :width: 800
   :align: center

|

Give the group a name and a description (see Figure 3) and click the create group button |create_group|.
The dialog will close and the group will be added to the navigation panel (see Figure 4).

|

.. image:: /_static/imgs/F4.png
   :width: 800
   :align: center

|

To add a file to a group, select the Add File Button |add| located on the header of the created group (see Figure 5).
The Add a Thredds Server File dialog will appear (shown in Figure 6).

|

.. image:: /_static/imgs/F5.png
   :width: 800
   :align: center

|

.. image:: d/_static/imgs/F6.png
   :width: 800
   :align: center

|

Enter a name and a description for the file. If the file requires user credentials (i.e. username and password) to
access, skip down and complete the section labeled Enter User Credentials for Files and then return and continue from
this point. Enter a URL for the THREDDS Catalog where the file is accessible. Click the Access Catalog Button |url_go| to
connect to the THREDDS Catalog.

A separate dialog will appear listing the files and folders contained in the catalog at the specified URL
(see Figure 7). Select a file or folder. If a folder is selected, the contents of the folder will be displayed in
the dialog. If a file is selected, the variables, dimensions, and metadata for the file will be retrieved and
loaded into the Add a Thredds Server File dialog (see Figure 8).

|

.. image:: /_static/imgs/F7.png
   :width: 800
   :align: center

|

.. image:: /_static/imgs/F8.png
   :width: 800
   :align: center

|

All the variables with two or more dimensions will be listed. Select the variables that you want included in the app
and click the Add Thredds File button. The file will be added to the navigation panel under the group to which it
was assigned (see Figure 9).

|

.. image:: /_static/imgs/F9.png
   :width: 800
   :align: center

|

Enter User Credentials for File
-------------------------------

Many datasets require a username and password to access the THREDDS Server. This feature was specifically added to the
app to allow access to data stored on the GES DISC data portal but it should be compatible with any server requiring
authentication. While the Add a Thredds Server File dialog is open, click the Link Authentication Credentials button |auth_btn|.
The Authentication dialog will appear (see Figure 10). If authentication has already been added to the app, click the
radio button next to the authentication you want to be associated with the app. To add authentication, fill in the
blanks in the Machine, User, and Password columns and press the add button |auth_add|. Click the radio button next to the newly
added authentication and click save |save|.

|

.. image:: /_static/imgs/F10.png
   :width: 800
   :align: center

|

Data Discovery
--------------

To visualize the data on the map, select a file from the Navigation Panel (see Figure 11). The file will appear on the
map and the Graph Window will open (see Figure 12).

|

.. image:: /_static/imgs/F11.png
   :width: 800
   :align: center

|

.. image:: /_static/imgs/F12.png
   :width: 800
   :align: center

|

The first variable listed in the file will be selected by default. The selected variable can be changed using the
Variable dropdown. The dimensions associated with the variable will be listed along with the range of values spanned
by each dimension. If the dimension is not a temporospatial dimension, the value associated with the dimension can
be specified using the appropriate dropdown.

How the data is displayed on the map can be modified by changing the display settings located at the bottom of the
Graph Window. Set Data Bounds specifies the data values over which the color range on the map spans. The color style
can be specified using the Set Color Style dropdown. The opacity of the data on the map can be set using the Set Layer
Opacity slider. Once the display setting are set to your liking, click the Update Display Settings button |display|.

|

.. image:: /_static/imgs/F13.png
   :width: 800
   :align: center

|

Data can be extracted at a point or over a user defined polygon. To extract the data at a point, create a point on
the map using the Create Marker |marker| tool located on the drawing menu in the map window. The Create Rectangle |rectangle| or Create
Polygon |polygon| tools can be used to define a polygon over which to extract the data. To use a shapefile to define a polygon,
change the Mask Data With |shp_dropdown| dropdown to Use A Shapefile. The Select a Shapefile dialog will open (shown in Figure 14).
If the shapefile has previously been uploaded to the map, check the radio button next to the desired shapefile and
click the Use Shapefile button |use_shp|.

|

.. image:: /_static/imgs/F14.png
   :width: 800
   :align: center

|

To upload a new shapefile, click the Upload Shapefile button |upload_shp|. Follow the prompts to upload the file, click the radio
button next to the uploaded file, and click the Use Shapefile button.

|

.. image:: /_static/imgs/F15.png
   :width: 500
   :align: center

|

Once a location over which to extract the data has been specified, click the Plot Time Series button |plot| to extract and
graph the data. It may take several minutes to retrieve the data, depending on the current network speeds.
The time series will be plotted in the graph window (see Figure 16).

|

.. image:: /_static/imgs/F16.png
   :width: 800
   :align: center

|

The time series can be downloaded as a csv or json file. Open the Download Data dropdown |download| and select the desired format.
An HTML file can also be downloaded which contains a web map that shows the same data that is displayed in the map
window. The last download option is to download a python notebook with code to extract the time series for the file
and variable currently selected in the MDE.

|

.. image:: /_static/imgs/F17.png
   :width: 800
   :align: center

|

There are two more tabs in the graph window which can be examined by clicking the Move Right arrow |right_arrow| located to the
right of the graph window. The first tab shows the metadata contained in the file (see Figure 18). The second tab
shows all the variables in the file with the associated dimensions (see Figure 19). The metadata for each variable
can be seen by clicking the Metadata Info button |info|. A dialog will open showing the variable metadata (see Figure 20).

|

.. image:: /_static/imgs/F18.png
   :width: 800
   :align: center

|

.. image:: /_static/imgs/F19.png
   :width: 800
   :align: center

|

.. image:: /_static/imgs/F20.png
   :width: 800
   :align: center

|

NetCDF Formatting Requirements
******************************

NetCDF files are one of the most popular formats for storing and distributing meteorological or earth observational
data. They have several advantages over other common file formats. The netCDF format is notable for its ease of use,
portability, simple data model, and strong user support. The netCDF format is made to be highly flexible, allowing
users to define and organize the data as they see best while still allowing the data to be shared across machines
and be self-describing, i.e. the data is human readable without reference to an external source.

Within the Met Data Explorer, the data displayed and analyzed in the app are retrieved from netCDF files that are
read from a THREDDS Data Server. To be compatible with the THREDDS Data Server and the services it provides which
the Met Data Explorer uses, the netCDF files on the THREDDS Data Server must be CF compliant
(the Climate and Forecast (CF) conventions are recommendations and standards for netCDF files) and adhere to
several additional guidelines.

This document outlines the CF conventions and additional guidelines to make netCDF files compatible
with the Met Data Explorer.

Dimension Names
***************
Many gridded datasets are spatiotemporal in nature, meaning that the data spans both space and time.
These datasets will have at least two spatial dimensions, defining a location on the earth, and a temporal dimension,
defining a point in time. These dimensions must be named correctly or the Met Data Explorer will not be able to parse
the dimensions correctly.

The dimension spanning the abscissa axis must contain x, lon, or longitude. We recommend naming this dimension x.
The dimension spanning the ordinate axis must contain y, lat, or latitude. We recommend naming this dimension y.
The time dimension must contain time or date. We recommend naming the temporal dimension time. If multiple dimensions
of the same type are needed, add an increasing number to the dimension name (e.g. time, time1, time2).
Additional dimensions (such as height, pressure, ect.) do not require specific names, but should be logical and
understandable.

|

.. image:: /_static/imgs/F21.png
   :width: 800
   :align: center

|

Variables for Dimensions
************************
Every dimension in the netCDF file that contains values must have a corresponding variable that has the exact same
name as the dimension to which it corresponds. If there is a dimension named x then there must be a variable named
x, if there is a dimension named time then there must be a variable named time, ect. The dimension defines the shape
(number of values) and the variable lists the values, attributes, and other information for the dimension.
Each dimensional variable should contain certain attributes. The attributes that should be in each dimensional
variable are long_name - a descriptive name for the dimension that is human readable, standard_name - a standardized
name for the dimension (i.e. if using EPSG4325 the standard_name should be longitude for the x dimension and latitude
for the y dimension), units - the units used for the dimension (if latitude and longitude are used the units should be
degrees_north and degrees_east respectively), and calendar - specifying on which calendar the time dimension is based
(only needed for the time dimension).

|

.. image:: /_static/imgs/F22.png
   :width: 800
   :align: center

|

Coordinate Reference Systems
****************************

All georeferenced data must be defined by a standard coordinate reference system
(crs). If the data does not conform to a standard crs then it cannot be transformed to be used with shapefiles or other
data. As an example, if latitude and longitude are used for global data, the latitude values must span from -90° to 90°
(not 0° to 180°) and longitude values must span from -180° to 180° (not 0° to 360°). This matches the standard crs
EPSG 4326.

|

.. image:: /_static/imgs/F23.png
   :width: 800
   :align: center

|

NCML Files
**********

NetCDF Markup Language (ncml) is an xml file type specifically designed for modifying, reformatting, and aggregating
netCDF files. The easiest way to reconfigure netCDF files is often to create a ncml file. Below are some useful
elements for creating a ncml file.

|

.. image:: /_static/imgs/F24.png
   :width: 800
   :align: center

|
Additional Resources
********************

- `MDE Source Code <https://github.com/BYU-Hydroinformatics/Met-Data-Explorer>`_

- `Grids Source Code <https://github.com/rileyhales/grids>`_

- `Grids Documentation <https://tsgrids.readthedocs.io/en/stable/>`_

- `Grids Demo <https://gist.github.com/rileyhales/79761303df16127e0195e11425fc2d9d>`_

- `CF Conventions <https://cfconventions.org/cf-conventions/cf-conventions.html>`_

- `NCML Cookbook <https://docs.unidata.ucar.edu/thredds/ncml/current/ncml_cookbook.html>`_
