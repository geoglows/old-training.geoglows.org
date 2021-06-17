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



