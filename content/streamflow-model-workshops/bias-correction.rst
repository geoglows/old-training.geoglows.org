Bias Correction
---------------

Click here to view a presentation that introduces the bias correction process: https://docs.google.com/presentation/d/1XZ15eqWV1hT4UdX9DxLjctpyS0Bb2G8UGg5oYnuaKQw/edit?usp=sharing

Bias Correction Workshop: https://colab.research.google.com/drive/15MUTx3lb5P93BLUv8Uehv0gTudc43qkX?usp=sharing

If you have observed streamflow data, you can add it to the bias correction tool through a csv file and view corrections
for the simulated data.

Upload your csv file
=====================

1. For the river we have been using, you can download the data file with the following link: https://www.hydroshare.org/resource/d222676fbd984a81911761ca1ba936bf/data/contents/Discharge_Data/23187280.csv
2. On the main part of the GEOGloWS Hydroviewer go to Bias Correction and select Upload New Observation

.. image:: /_static/imgs/streamflow-services/upload-bias-correction.jpg
   :width: 700

3. From there you can choose the downloaded file and then select submit

Select a River
==============
1. Close out and select the river with the same Reach ID 9004355

2. From there, select the bias correction tab and Start Bias Correction
If you have more than one csv file you may have to select the csv file you uploaded under Uploaded Observational Data before you start your bias correction

.. image:: /_static/imgs/streamflow-services/start-bias-correction.png
   :width: 700

The data are uploaded, compared to the simulated, and bias-corrected as seen in the figures below
Under the bias correction tab you can view the bias corrected cumulative volume comparison through observed data (your uploaded csv file), the simulated data (the original data from the program) and the corrected simulated data.

.. image:: /_static/imgs/streamflow-services/bias-data-compared.png
   :width: 700

If you scroll down there is also a bias correction scatter plot as well as a table that compares the original full time series to the corrected full time series

.. image:: /_static/imgs/streamflow-services/bias-correction-scatter-plot.png
   :width: 700

Bias Corrected Flow Duration Curve
**********************************

.. image:: /_static/imgs/streamflow-services/bias-corrected-flow-curve.png
   :width: 700

Average Flows
*************

.. image:: /_static/imgs/streamflow-services/average-flows.png
   :width: 700

Historical
**********

.. image:: /_static/imgs/streamflow-services/historical.png
   :width: 700

Forecasts
*********

.. image:: /_static/imgs/streamflow-services/forecasts.png
   :width: 700
