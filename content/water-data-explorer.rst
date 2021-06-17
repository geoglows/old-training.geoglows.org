WHOs Water Data Explorer
========================

Introduction
------------

In recent years, there has been a growing need for standardized ways of sharing water data on the web. In response, the
Consortium of Universities for the Advancement of Hydrologic Science (CUAHSI) has developed the Hydrologic Information
System (HIS) along with the standardized WaterOneFlow web services and WaterML data exchange format. Tools to access
data shared to the `WaterOneFlow services and WaterML already exist such as the Microsoft Windows HydroDesktop software <https://www.sciencedirect.com/science/article/pii/S1364815212001053>`_,
`WaterML R package <https://github.com/jirikadlec2/waterml>`_, and the web-based `CUAHSI HydroClient <https://data.cuahsi.org/>`_
which serves as an access point to the `CUAHSI HIS <http://hiscentral.cuahsi.org/>`_ database.

The Tethys Water Data Explorer (WDE) is a newly developed web-based tool allowing a broad range of users to discover,
access, visualize, and download data from any Information System that makes available water data in WaterML format
through WaterOneFlow services. WDE is designed in a way that allows users to customize it for local or regional web
portals.

Functionalities
---------------

User Interface
**************

To organize and manage various WaterOneFlow web services, WDE uses Data Views that are organized in Catalogs.

.. image:: /_static/imgs/water-data-explorer/views-catalogs.png
   :width: 700

Catalogs contain different data views that contain a set of data accessible through a specific WaterOneFlow web service.
The stations with accessible data are displayed on the WDE map interface along with a legend of the respective Data
Views.

.. image:: /_static/imgs/water-data-explorer/selected-view.png
   :width: 700

For each station, a set of metadata is available in the Graphs Panel. There is additionally, a table of observed
variables for each Station, including variable names, units, and interpolation types.

.. image:: /_static/imgs/water-data-explorer/selected-station.png
   :width: 700

Time-series data can be plotted as either a “Scatter” or “Whisker and Box” plot. The data can also be downloaded in CSV,
`OGC NetCDF <https://www.ogc.org/standards/netcdf>`_, `OGC WaterML 2.0 <https://www.ogc.org/standards/waterml>`_, and
`CUAHSI WaterML 1.0 <https://his.cuahsi.org/wofws.html>`_ formats for any available time period in the Time Series Plots
section.

.. image:: /_static/imgs/water-data-explorer/time-series-plot.png
   :width: 700

Data Discovery
**************

The user can filter the available Views by Country and variable by using the green filter icon in the top left corner.

*Note* The user selects to only display the variables included by the selected countries by using the blue 'Update
Variables' button.

.. image:: /_static/imgs/water-data-explorer/update-variables.png
   :width: 700

.. image:: /_static/imgs/water-data-explorer/view-controls.png
   :width: 700

Data Analysis
*************

The WDE application uses a python package called “Pywaterml”. Pywaterml accesses the WaterOneFlow (WOF) web services and
retrieves the information in different formats. The Pywaterml can be used as a Python Notebook.

Users can open the Python notebook tutorial and the Pywaterml documentation by clicking on the Google Colab and the
green book icons.

For a selected view, users can open a Python notebook template in Google Colab. The Python notebook can also be
downloaded for a specific station or variable.

.. image:: /_static/imgs/water-data-explorer/anaylsis-tools.png
   :width: 700

Time Series Visualization and Downloading
*****************************************

To visualize and download time series available for a specific station, the user can select the station on the WDE map
interface, triggering the opening of the WDE Graphs Panel at the bottom of the application. Use the green bar graph icon
on the top right of the Graphs Panel to select the time series to be visualized or downloaded.

.. image:: /_static/imgs/water-data-explorer/graphs-panel.png
   :width: 700

*Note* User can hide or show the Graphs Panel by means of the bar graph icon on the right of the application
header. In the opened window, the user can select a variable of interest, plot type, and time period of interest.

WDE uses the Plotly library which provides the menu above, to allow users to download plots in PNG format, pan to, zoom
in/out, and autoscale plots.

Administrator Functionalities
-----------------------------

Adding and Deleting Data Catalogs and Views
*******************************************

Users can add catalogs to the WDE. The blue and white plus button will access the “Add a Catalog of Views” menu.

.. image:: /_static/imgs/water-data-explorer/add-catalog.png
   :width: 700

To add a new Catalog of Views, administrators should enter its title, description, and endpoint if available.

*Note* To add a Catalog that is already published and accessible through WaterOneFlow web services, administrators
should enter the Catalog endpoint to automatically import its Views. Administrators can check the available Views by
using the blue 'Check Services' button.

To add Views to a specific Catalog, administrators should use the blue and white plus button to the right of the
Catalog’s title to access the “Add Views to Catalog” menu.

.. image:: /_static/imgs/water-data-explorer/add-views.png
   :width: 700

The blue trash can button will access the “Delete Views” menu, allowing admins to delete views by selecting the view to
be deleted.

.. image:: /_static/imgs/water-data-explorer/delete-views.png
   :width: 700

The red trash can button will access the “Delete Catalogs” menu, where admins can delete catalogs by selecting the
Catalog to be deleted.

.. image:: /_static/imgs/water-data-explorer/delete-catalogs.png
   :width: 700

Customizing the WDE User Interface
----------------------------------

To customize the WDE user interface, select the grey settings icon.

.. image:: /_static/imgs/water-data-explorer/customize.png
   :width: 700

In the Custom Settings table, admins can customize the name and logo of the WDE to suit the institution using it. They
can also change the boundaries of the map interface.









