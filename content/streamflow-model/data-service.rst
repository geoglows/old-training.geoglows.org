Data Service (REST API)
=======================

The REST API allows you to query and download information for any stream based on forming a query with parameters as
part of the URL. Documentation for the possible queries and how to form them is found on the main GEOGloWS Streamflow service
page https://geoglows.ecmwf.int/. The following workshop provides a brief overview of how the services are used.

REST API Documentation
----------------------

1. Go to this website where you can find the documentation for the REST API: https://geoglows.ecmwf.int
2. Click the tab on the top called “REST API Documentation”.
3. Click on the blue bar that says GET and the name of the streamflow API method.

.. image:: /_static/imgs/data-service-demo/get.png
   :width: 700

4. Press the white “Try it out” button located beneath the blue bar on the right side.

.. image:: /_static/imgs/data-service-demo/try-it-out.png
   :width: 700

5. Provide the necessary parameters. Usually, the only argument is either a reach_id or both a latitude and a longitude.

.. image:: /_static/imgs/data-service-demo/parameters.png
   :width: 700

6. Press the blue “Execute” bar.

.. image:: /_static/imgs/data-service-demo/execute.png
   :width: 700

7. The website will then generate the appropriate curl command and URL to access the data you chose with the parameters
you provided.

.. image:: /_static/imgs/data-service-demo/curl-request-url.png
   :width: 700

8. After retrieving the streamflow information from the REST API, it will be presented as a preview under code 200
(which is a common response code for a successful query). A download button is found on the bottom right of that box.

.. image:: /_static/imgs/data-service-demo/streamflow-information.png
   :width: 700

9. You can copy and paste the URL you found in step 6 into a new tab of your web browser to retrieve the same result
without needing to use the documentation’s interactive tool.

Forecasted Datasets
-------------------

Each day, a new 15-day weather prediction is made by ECMWF. The weather forecast is composed of 52 ensemble members.
From that weather prediction, a surface runoff estimation is made using the precipitation forecast and a land surface
model, HTESSEL. Each of the 52 ensemble members is used to drive the GEOGloWS ECMWF hydrologic model producing 52
streamflow predictions called *ensembles*. The results of these streamflow predictions are available through the following
methods.

**ForecastStats**: Summarizes the 52 ensembles across each time step by reporting the minimum flow, 25th percentile flow,
average flow, 75th percentile flow, and maximum flow. Returns a time series of values for each of the 5 statistical
values.

**ForecastEnsembles**: Returns a time series of flows for each of the 52 ensemble members.

**ForecastWarnings**: Returns a CSV that summarizes when streams are expected to reach 2-, 5-, 10-, 25-, 50-, and 100-year return period level flows.

**ForecastRecords**: Each day, the average of the predicted flows from 52 forecast ensemble members is recorded and can be
retrieved to see a longer running record of streamflow predictions.

Historically Simulated Datasets
-------------------------------

ECMWF provides the ERA5 historically simulated runoff dataset. This dataset is also used to drive the GEOGloWS ECMWF
model and produce a historical streamflow simulation. This streamflow simulation covers from January 1, 1979 to the
present with only a few months lag. The historical streamflow and products derived from it are available through the
following methods:

**HistoricSimulation**: Returns a time series of daily average streamflow from 1979 through the near present

**DailyAverages**: Returns a time series 366 steps long representing the average flow for each day of the year including
leap day. This is roughly equivalent to what an average year of streamflow looks like at the reach of interest.

**MonthlyAverages**: Returns a time series of 12 steps representing the average flow for each of the 12 months of the year
based on the historical simulation. Most useful in comparative analyses and validation metrics.

**ReturnPeriods**: Based on the historical simulation and the Gumbal distribution, returns an estimation of the 2-, 5-, 10-,
25-, 50-, and 100-year return period flows for the stream reach.