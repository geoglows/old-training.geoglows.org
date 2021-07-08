Historical Validation Example (Sample Data Provided)
====================================================

In this tutorial, we will show how to validate the GEOGloWS ECMWF Streamflow Service historical simulation using the
HydroStats tethys app.

Obtain Data
-----------

For running the historical validation you should first identify the stream of interest. You will need historical
observed and simulated streamflow data for this stream. For this tutorial, we will provide demo data for the Reach ID
9004355.

1. Use this link to download the demo historical observed data:
https://www.hydroshare.org/resource/d222676fbd984a81911761ca1ba936bf/data/contents/Discharge_Data/23187280.csv
If you are performing the validation using your own observed data, your data must have two columns with column headers
in the first row. The first column should be titled ‘datetime’ and contain dates in a standard format. The other may
have any title but must contain streamflow values in cubic meters per second (m^3/s).
The observed data csv should look like this:

.. image:: /_static/imgs/historical-validation/demo-data.png
   :width: 350

2. To get the historical simulation data, go to this url, which will access the API and download the historical simulation:
https://geoglows.ecmwf.int/api/HistoricSimulation/?reach_id=9004355&return_format=csv
If you are performing the validation for a different Reach ID, you may edit the Reach ID in the url above, or use the
GEOGloWS website to access the API. To use the interactive website, go to this link:
https://geoglows.ecmwf.int/documentation and click Get Historic Simulation. Click
“Try,” enter the Reach ID, and click “execute.” This will then give you the option to download the historical simulation.
The simulated data csv should look like this:

.. image:: /_static/imgs/historical-validation/simulated-data.png
   :width: 350

Open the Statistics Calculator App
-----------------------------------

Once we have the historic simulated data and the historic observed data we are able to run the historical validation.

1. Go to https://apps.geoglows.org

2. Open the Hydrostats App

.. image:: /_static/imgs/historical-validation/hydrostats-app.png
   :width: 700

| 3. Login with the Demo Account (case sensitive)
| a. Username: demo
| b. Password: demo

.. image:: /_static/imgs/historical-validation/streamflow-stats-calculator.png
   :width: 700

Preprocessing
-------------

#. First, we will plot the Historical Simulation data.

   a. Click on “Process a Time Series” on the left menu.
   b. Upload the historical simulation csv.

   .. image:: /_static/imgs/historical-validation/process-time-series.png
      :width: 700

   c. Click “Plot and Analyze Raw Data”

   .. image:: /_static/imgs/historical-validation/hydrograph.png
      :width: 700

   d. Notice that the historical simulation has no gaps and an even time-step.

#. Next, we will plot the Observed Data.

   a. Refresh the page “Process a Time Series Dataset”
   b. Upload the observed data file.

   .. note::

      If there are timesteps with empty values, this part will not work. You will need to remove the empty timesteps.
      The csv provided has empty values; you may skip this step if you don’t need to analyze the observed timeseries.

   c. Click “Plot and Analyze Raw Data”

   .. image:: /_static/imgs/historical-validation/plot-analyze-data.png
      :width: 700

   d. Notice that this timeseries has gaps. A summary is given showing the length and amount of gaps.

   .. image:: /_static/imgs/historical-validation/gaps-summary.png
      :width: 700

   e. If desired, you can interpolate the missing data. For this example, we won’t interpolate.

#. Click on “Merge Two Time Series” on the left menu.

   a. Upload the historic observed data and the historical simulated data downloaded for this tutorial.

   .. image:: /_static/imgs/historical-validation/merge-two-datasets.png
      :width: 600

   b. Click on “Plot Merged Data” to see the plot for observed and simulated data.

   .. note::

      Notice that the merged data only covers the time-steps that contain **both** the simulated and the observed data.

   c. Click on Download Merged Data to save a csv file with the merged data.

   .. image:: /_static/imgs/historical-validation/download-merged-data.png
      :width: 600

The critical thing for validating two datasets is to have a single .csv with both simulated and observed data merged.
There should be a one-to-one relationship so that every time step has a value for both observed and simulated in order
for the metrics to work correctly. There are some options to do this in the HydroStats App, but you may have to do some
of this work on your own. Once you have a merged data .csv file, you can perform the validation with metrics from
HydroStats.

Visualization
-------------

#. Click on “Validate Historical Data” on the left menu. This tab allows us to validate the historical simulation.
   a. Upload the Merge File you downloaded in the previous step.

   .. image:: /_static/imgs/historical-validation/validate-historical-data.png
      :width: 600

#. Click on:

   a. Create Hydrograph

   .. image:: /_static/imgs/historical-validation/hydrograph-entire-series.png
      :width: 700

   b. Then create Hydrograph of Daily Averages

   .. image:: /_static/imgs/historical-validation/hydrograph-daily-averages.png
      :width: 700

   c. Create Scatter Plot

   .. image:: /_static/imgs/historical-validation/scatterplot-best-fit.png
      :width: 550

   d. Create Scatter Plot with Log-Log Scale

   .. image:: /_static/imgs/historical-validation/scatterplot-log-scale.png
      :width: 550

Analysis
--------

1. Scroll down a little more on the “Validate Historical Data” page. You will see a “Table” section and right below that
   we can select the metrics of interest to validate the streamflow prediction tool historical simulation compared with the
   observed data.

   a. In this case we are going to select:

      * Mean Absolute Error, Root Mean Square Error, Nash-Sutcliffe Efficiency, King-Gupta Efficiency (2012).

      .. note::

         Leave all of the King-Gupta Efficiency (2012) parameters at the default setting

   b. Finally, click on “Make Table” to see the report.

   .. image:: /_static/imgs/historical-validation/make-table.png
      :width: 700

   .. image:: /_static/imgs/historical-validation/table-metrics.png
      :width: 700

2. Make a new table, with metrics of your choice.

   a. See this full `list <https://hydrostats.readthedocs.io/en/stable/ref_table.html>`_ of metrics.

3. If we click on “Compare Volume” we can compare the simulated hydrograph and the observed hydrograph volumes to get a
rough estimate of water balance.

   .. image:: /_static/imgs/historical-validation/volume.png
      :width: 700







