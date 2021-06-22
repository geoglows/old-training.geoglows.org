Historical Validation
=====================

The historical validation workshops will showcase some of the validation work we have done in different pilot regions.
More importantly these workshops will guide you on how you can use your own local observations to evaluate the
performance of the model for your rivers.

`Historical Validation Studies and Methods <https://docs.google.com/presentation/d/1rPriBch8Dr72Cx5nK2nayFLH60NvH7-qqawBdEXsXTA/edit?usp=sharing>`_

`How to Perform Historical Validation Using Your own Observation Data <https://colab.research.google.com/drive/14u9aMkf7_SnRdlmner5LdmG_ZfvrAGkL>`_

Tutorial
--------

A GEOGloWS ECMWF Streamflow Services generates a historical simulation from 1979-present based on weather data records.
However, the model often has bias, commonly overpredicting streamflow. When observed streamflow data is available on a
stream, we can use that data to improve the historical simulation and forecast model. This process is called bias
correction.

This tutorial will show you how to perform a bias correction on streamflow data using the Global Hydroviewer Web App.

Obtain Data
-----------
1. We will need observed streamflow data. You may use your own observed data if you wish, or the demo data available
here: https://www.hydroshare.org/resource/d222676fbd984a81911761ca1ba936bf/data/contents/Discharge_Data/23187280.csv.

2. If you are using your own observed data, it should be saved as a .csv file that has 2 columns and both should have
column labels in the first row. The first column should be titled ‘datetime’ and contain dates in a standard format.
The second column may have any title but **must** contain streamflow values in cubic meters per second (m^3/s).

.. image:: /_static/imgs/historical-validation/csv-file-format.png
   :width: 300

Inputting Data
--------------

1. Go to the GEOGloWS ECMWF Streamflow Hydroviewer:  https://geoglows.apps.aquaveo.com/apps/.

2. After opening the Hydroviewer app, find the river segment you would like to do the bias correction on. You can do
this either by searching for a Reach ID or latitude/longitude coordinates using the fields on the left or by zooming to
the river. If you are using the demo data, use the Reach ID 9004355.

.. image:: /_static/imgs/historical-validation/reach-id.png
   :width: 700

3. Once you have found the river, click on it to pull up the forecast. This may take a few minutes to load. Then go to
the Bias Correction tab at the top of the window.

.. image:: /_static/imgs/historical-validation/bias-correction-tab.png
   :width: 700

4. Now you can upload your observed data csv file by clicking on the blue “Upload New Observation” button and select the
data you want to upload. Once you have a file uploaded, click “Start Bias Correction.”

.. image:: /_static/imgs/historical-validation/upload.png
   :width: 700

5. Running the bias correction generates a plot of cumulative volume and a scatter plot to show how the bias correction
improved the Historical Simulation. You can turn the different lines and datasets on and off by clicking their label in
the legend. A table of error metrics is also generated. Each error metric describes a different aspect of how correlated
the datasets are; you can read more about the error metrics here: https://hydroerr.readthedocs.io/en/stable/list_of_metrics.html

.. image:: /_static/imgs/historical-validation/volume-comparison.png
   :width: 700

.. image:: /_static/imgs/historical-validation/scatter-plot.png
   :width: 700

.. image:: /_static/imgs/historical-validation/table.png
   :width: 550

6. After running the bias correction, you can also go to the Historical tab, where a plot of the original simulated
data, observed data, and corrected simulated data is generated.

.. image:: /_static/imgs/historical-validation/corrected-simulation-comparison.png
   :width: 700

7. Finally, you can go to the Forecasts tab, where a plot of the bias corrected forecast is generated.

.. image:: /_static/imgs/historical-validation/corrected-streamflow.png
   :width: 700